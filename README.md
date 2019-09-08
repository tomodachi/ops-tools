# ops-tools
A collection of programs for ops related tasks

---

***downtime_scheduler:***  
nagios is just to much clicking!!  
cmd line tool allows you to downtime 
one multiple or batches of hosts!!!

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
---

***build_inv:***  

because sometimes we treat infra as snowflakes!  
builds ansible inventory file 
builds ssh config inventory file

- multi az / region / aws account support  
- excluding instances with filters based on hostname or tags

```
Build Ansible / SSH inventory to stdout                         
Use AWS main creds to generate for all accounts

optional arguments:
  -h, --help            show this help message and exit
  -a, --ansible         build ansible inventory file
  -s, --ssh             build ssh config file
  -ns, --no-ssh         don't include custom ssh config
  -nx, --no-exclude     disable exclude list
  -u DEFAULT_USERNAME, --user DEFAULT_USERNAME
                        include specified user in each entry
  -i DEFAULT_IDENTITY_FILE, --identity DEFAULT_IDENTITY_FILE
                        include identity file in each entry
```
***umanager:***
Batch account user management for AWS IAM accounts & FreeIPA.  
For easier scripting & automation.    
Depends on [ipahtttp](https://github.com/nordnet/python-freeipa-json)

```
usage: umanager [-h] [-d D_USERNAMES] [-a A_USERNAME] [-f FIRST] [-l LAST]
                [-ls L_USERNAMES] [-u IPAUSER] [-s SERVICE] [-ag AWS_GROUPS]
                [-nc]

Add / Disable / list IPA/AWS accounts

optional arguments:
  -h, --help            show this help message and exit
  -d D_USERNAMES, --disable D_USERNAMES
                        disable a user(s) in all systems
  -a A_USERNAME, --add A_USERNAME
                        add a single user in all systems
  -f FIRST, --first FIRST
                        first
  -l LAST, --last LAST  lastname
  -ls L_USERNAMES, --list L_USERNAMES
                        list users services -ls all for all users
  -u IPAUSER, --username IPAUSER
                        ipa username from cmdline
  -s SERVICE, --service SERVICE
                        ipa|aws
  -ag AWS_GROUPS, --aws-group AWS_GROUPS
                        aws groups to add user to
  -nc, --no-color       disable color otput
```
