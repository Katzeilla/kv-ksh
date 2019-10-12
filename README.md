## kv-ksh 

-----------------

**About**

 - tiny file based key/value database for ksh
 - databases store in home directory
 - each user has 1 database by default


**Usage**

Import 5 ksh functions via . (dot)

```
$ . ./kv-ksh
```
 
**Requirements**

Unix-like environement, ksh, no dependencies


**Use database functions**

```
$ kvset <key> <value>      # create or change value of key
$ kvget <key>              # get value of key
$ kvdel <key>              # delete by key
$ kvlist                   # list all current key/value pairs
$ kvclear                  # clear database
```

**Examples**

``` 
$ . ./kv-ksh
$ kvset user mr.bob
$ kvset pass abc@123
$ kvlist
user mr.bob
pass abc@123
$ kvget user
mr.bob
$ kvget pass
abc@123
$ kvdel pass
$ kvget pass

$ kvclear
```

**Run tests**

```
git clone https://github.com/katzeilla/kv-ksh.git
cd kv-ksh
./kv-test
```

#### Test result:

```

RUN ALL TEST CASES:
===================
  1 call kvget for non-exist key should return empty  OK
  2 kvset then kvget a variable                       OK
  3 kvset then kvset again with different value       OK
  4 deleted variable should be empty                  OK
  5 kvdel non exist should be OK                      OK
  6 kvset without param return error                  OK
  7 kvget without param return error                  OK
  8 kvdel without param return error                  OK
  9 kvset 3 keys/value; kvlist => line count = 3      OK
 10 non-exist-var => empty value => line count = 1    OK
 11 kvclear; kvlist => line count = 0                 OK
 12 kvget return empty value => error code != 0       OK
 13 spaces in value                                   OK


```

#### Credit 

Forked from https://github.com/damphat/kv-bash
