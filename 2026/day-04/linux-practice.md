
Process checks

View active processes
ps aux | head -10

Search for a specific process
pgrep -a ssh

Service checks

Check service status
systemctl status ssh

 List all active services
systemctl list-units --type=service --state=running

Log checks

view logs for ssh service
journalctl -u ssh --since "1 hour ago"

View last 20 system log entries
tail -n 20 /var/log/syslog

Mini troubleshooting steps

Check if process exists:
pgrep sshd

Check service status:
systemctl status ssh
