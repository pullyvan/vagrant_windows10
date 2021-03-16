# Ansible Windows 10 Vagrant 

Ansible playbooks for Windows 10 Vagrant

## Notes

### Run Vagrantfile

Once the Vagrantfile downloaded
```
git clone git@github.com:pullyvan/vagrant_windows10.git
cd vagrant_windows
vagrant up
```

### To use ansible do not forget to adapt the ip in inventory
```
ansible-playbook -i inventory main.yaml
```
### Troubleshoot
#### Ping
Windows 10 vagrant is not pinging, you may need to enable ping in powershell
##### For IPV4
```
netsh advfirewall firewall add rule name="ICMP Allow incoming V4 echo request" protocol=icmpv4:8,any dir=in action=allow
```
##### For IPV6
```
netsh advfirewall firewall add rule name="ICMP Allow incoming V6 echo request" protocol=icmpv6:8,any dir=in action=allow
```
#### Python crash when run on MacOS High Sierra or Higher
run this command in your current terminal
```
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
```