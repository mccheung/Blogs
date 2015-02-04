Where is the cron log file in MacOSX Lion
==============================================


### Much easier to simply add the following to /etc/syslog.conf :

    cron.* /var/log/cron.log

### Then restart syslog

    sudo launchctl unload /System/Library/LaunchDaemons/com.apple.syslogd.plist
    sudo launchctl load /System/Library/LaunchDaemons/com.apple.syslogd.plist


Test on OS X 10.9.2, It's works well
