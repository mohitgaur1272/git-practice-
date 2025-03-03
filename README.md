# first of all you have to ceate ssh-key with  ```ssh-keygen -t rsa -b 4096``` this command use jenkins user and copy id_rsa.pub and paste on your all private servers in ```.ssh/authorized_keys``` this file.
## after that you can ssh with 

```
ssh username@<private-ip>
```
## if you are unable to login with this command so use the your .pem file so copy you .pem file data and create in your jump server.pem file and paste the data in this file then use this command 
```
ssh file.pem username@<private-ip>
```
## then you have to create servers.txt file given below location and you have to add in this file all ips of your private servers 
```
sudo cat /var/lib/jenkins/servers.txt 
```
like
```
10.20.2.132
10.20.2.106
10.20.2.112
10.20.2.109
```

## and then you have to create global credentials in jenkins and 
## in this id you have to set ```username=ec2-user``` and ```password=/var/lib/jenkins/.ssh/id_rsa``` file data 
```
SSH_CREDENTIALS = 'server-ssh-key'
```
