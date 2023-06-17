###  Cloud Watch
 
# Checking instance metrics
- Just select the instance and go to the monitoring tab
- you can check all the metrics there.

# cloudwatch metrics

- Go to the cloud watch console and select all metrics from the left navigation bar.
- In the browse tab select/search the custom namespace
- search for the cloudwatch namespace
- Search for the specific metric like cpu/memory/CPU_USAGE_IDLE
- click on the actions tab above the displayed graph and click on create dashboard.
- give a name to the dashboard and select bar/line etc as widget type

## cloudwatch alarms

- Click on alarms in left navigation pane.
- click on new alarm.
- click on select metric
- On the Browse tab, in the Metrics search box, type:
CPU_USAGE_IDLE
and press Enter
- select the server that you wish to create alarm for
- select the conditions for the alarm to start
- In the configure actions tab
      - create a new sns topic
      - subscribe to the topic

- In the name and configure provide a name to the alarm
- and review and create.

  
