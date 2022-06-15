Create a Watcher
================

Watcher is an Elasticsearch feature that you can use to create actions based on conditions, which are periodically evaluated using queries on your data. Watches are helpful for analyzing mission-critical and business-critical streaming data. For example, you might watch application logs for performance outages or audit access logs for security threats.

#. Configure Elastic Watcher (in the Stack Management Menus -> Alerts and Insights -> Watcher)

     .. image:: ../images/Event/Picture5.png
#. Click Create -> Create Advanced Watch

     .. image:: ../images/Event/Picture6.png
#. Enter a name and paste JSON code from black text box (Next Page) into “Watch JSON” replacing all data then click “Create Watch” at the bottom.

     .. image:: ../images/Event/Picture7.png

     .. code-block::

       {
          "trigger": {
            "schedule": {
              "interval": "5m"
            }
          },
          "input": {
            "search": {
              "request": {
                "search_type": "query_then_fetch",
                "indices": [
                  "awaf-*"
                ],
              "rest_total_hits_as_int": true,
              "body": {
                "query": {
                  "bool": {
                    "must": [
                      {
                        "match": {
                          "request_status.keyword": "alerted"
                        }
                      },
                      {
                        "terms": {
                          "severity.keyword": [
                            "Critical",
                            "Error"
                          ]
                        }
                      },
                      {
                        "terms": {
                          "geoip.country_code2.keyword": [
                            "CN",
                            "KP",
                            "RU"
                          ]
                         }
                       },
                       {
                         "range": {
                           "@timestamp": {
                             "gte": "now-5m",
                             "lte": "now"
                           }
                         } 
                       }
                     ]
                   }
                 }
               }
             }
           }
         },
         "condition": {
           "compare": {
             "ctx.payload.hits.total": {
               "gt": 0
             }
           }
         },
         "actions": {
           "logstash_exec": {
              "webhook": {
                "scheme": "http",
                "host": "localhost",
                "port": 9001,
                "method": "post",
                "path": "/{{watch_id}}",
                "params": {},
                "headers": {},
                "body": "{{ctx.payload.hits.hits[0].clientip}}"
              }
           }
         }
       }
#. Ensure that the Watcher state is OK

     .. image:: ../images/Event/Picture8.png