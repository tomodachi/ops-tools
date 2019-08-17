# ops-tools
A collection of programs for ops related tasks

***downtime_scheduler:***  
nagios is just to much clicking!!  
cmd line tool allows you to downtime one, multiple or batches of hosts!!!

```
usage: downtime_scheduler [-h] [-l] [-s SINGLE] [-b {batch2,batch1}]
                          [-m [MINUTES]] [-msg [MESSAGE]] [-dt DATETIME] [-v]

optional arguments:
  -h, --help            show this help message and exit
  -l, --list            list batches
  -s SINGLE, --single SINGLE
                        specify comma separated hosts
  -b {batch2,batch1}, --batch {batch2,batch1}
                        batch schedule
  -m [MINUTES], --minutes [MINUTES]
                        downtime in min. default 20/60 for single/batch
  -msg [MESSAGE], --message [MESSAGE]
                        custom downtime msg
  -dt DATETIME, --datetime DATETIME
                        start date time in UTC format: '1970-01-01 16:16:12'
  -v, --verbose         Verbose responses from Nagios
```
