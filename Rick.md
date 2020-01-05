# 2nd Lesson
## Windows Subsystem for Linux 
Read the Microsoft Documentation here:  
[WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
Enable the Feature in an administrative powershell window (aka. run as Administrator)
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux  
```
Run the following commans in a regular Powershell Window. (If you run them in the same Window
with Admin Privileges, then only Admins will be able to run the Linux Subsystem)

```
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1604 -OutFile Ubuntu.appx -UseBasicParsing\
Rename-Item Ubuntu.appx Ubuntu.zip <br/>
Expand-Archive Ubuntu.zip Ubuntu  
cd Ubuntu  
.\ubuntu.exe  
```



## Installing the AWS CLI
Read the Documentation here [AWS CLI](https://aws.amazon.com/cli/)
I recommend installing the AWS CLI onto the system Python installation, instead of using a 
virtualenv and pyenv. This is because you or services/bash scripts that you will write 
might run from any location. So you won't have to worry about activating a virtualenv or 
messing with the PATH Environment variable.

After successful installation we configure it and test it.
Configuration run: `aws configure` 
this creates two files  `~/.aws/config` and `~/.aws/credentials/`

### Aws Cli usage
Getting user information
`aws iam get-user`

or for a specific user
`aws iam get-user --user-name user1`

### AWS Cli security groups and jq
`jq` is a command line tool to parse json in bash. See [jq](https://stedolan.github.io/jq/)
On Ubuntu/Debian `apt install jq` does the trick.
For example select all _FromPort_s with `aws cli` and `jq` like this:
```
aws ec2 describe-security-groups | jq '.SecurityGroups[].IpPermissions[].FromPort'
```

## Linux Firewalls and security
[Linode Link](https://www.linode.com/docs/security/firewalls/configure-firewall-with-ufw/)
