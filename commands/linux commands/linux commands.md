
account management

display usernames

``cut -d: -f1 /etc/passwd
`awk -F: '{print $1}' /etc/passwd

# check groups

groups

``getent group lxd
lxd:x:1001:soc




