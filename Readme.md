
### RsyslogLobackSpike ###

Configure in your `logback.xml` with correct ip or host name.

Go to your remote machine and install `rsyslog`.

In file `/etc/rsyslog.conf` (I am using ubuntu) uncomment udp related lines as following:

    # provides UDP syslog reception
    $ModLoad imudp
    $UDPServerRun 514
    
Edit file `/etc/rsyslog.d/50-default.conf/etc/rsyslog.d/50-default.conf` as following:

    #
    # Logging for my rsyslog spike
    #
    local1.*                        /var/log/spike/spike.log
    
Restart rsyslog:

    sudo service rsyslog restart
    
Run the app and see the results in the file specified above.

Troubleshooting (useful links):
 
 http://stackoverflow.com/questions/29548028/whats-wrong-with-my-logback-syslog-appender
 
 http://stackoverflow.com/questions/10161809/trying-to-debug-issue-with-logback-syslog-appender-not-updating-syslog
