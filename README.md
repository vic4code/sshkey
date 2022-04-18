# sshkey - automatic remote login
Create ssh key for remote login without entering password.

## At local 
### Step 1. ssh-key generation 
```
$ ssh-keygen -t rsa -C "your_email@example.com" 

Generating public/private rsa key pair.
Enter file in which to save the key (/home/username/.ssh/id_rsa):

Enter passphrase (empty for no passphrase):
Enter same passphrase again:

Your identification has been saved in /home/username/.ssh/id_rsa_ubuntu.
Your public key has been saved in /home/username/.ssh/id_rsa_ubuntu.pub.
The key fingerprint is:
SHA256:nNnQckFbuegUs4WD3y+7YqwCaDhfUlX2J17jxF7X3FU xenby@demo.com
The key's randomart image is:
+---[RSA 2048]----+
|       .o++ ..  E|
|      .  *o+.  ..|
|     .  = *+ o ..|
|    .  . Ooo+ * +|
| . o    Soo..B o.|
|o + o     . ..o  |
| + o .   .  . .  |
|  .   .   +  o   |
|       ..o .o.   |
+----[SHA256]-----+
```

### Step 2. cat and copy the generated public rsa key:
```
$ cat ~/.ssh/id_rsa.pub 

>> ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDOZypQABxuCschD6jjRZFr1iPCqzrpo40Mzw6vXRfPlFwF9QJhLm3YYdtnpVekj9e1Y4kUduM924PAiLgfRw/6AJ1ueDR1BEDLeH8gAV1Cc90oPUvitYItPN8F1HrqiT37GZ3wKWKIFw70NL8Hs6BL61F+LgFmfXQDRyp7IIcyK9rmk24yqLSue/DiSbA0y85E4uvV7ekZD2NXeA9AnKHFe/cy614SQv2NNQCwi2ZRuP25du9xGVv0QvCwrZ4ANJky9V7xlO4dFFHqcNXUPQUm8EeRxySVCdTbenqiEQ3flLVBCCCxvnc7ApHlLNc/CZSpcft96xfGB3qOCrRvjb2/ xxxx@demo.com
```

## At remote
### Step 3. Create `authorized_keys` file to `~/.ssh/` and paste the public key to the `authorized_keys` file:
```
echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDOZypQABxuCschD6jjRZFr1iPCqzrpo40Mzw6vXRfPlFwF9QJhLm3YYdtnpVekj9e1Y4kUduM924PAiLgfRw/6AJ1ueDR1BEDLeH8gAV1Cc90oPUvitYItPN8F1HrqiT37GZ3wKWKIFw70NL8Hs6BL61F+LgFmfXQDRyp7IIcyK9rmk24yqLSue/DiSbA0y85E4uvV7ekZD2NXeA9AnKHFe/cy614SQv2NNQCwi2ZRuP25du9xGVv0QvCwrZ4ANJky9V7xlO4dFFHqcNXUPQUm8EeRxySVCdTbenqiEQ3flLVBCCCxvnc7ApHlLNc/CZSpcft96xfGB3qOCrRvjb2/ xxxx@demo.com" >> ~/.ssh/authorized_keys
```

### Last step:
```
chmod -R go= ~/.ssh
chown -R username:username ~/.ssh
```

### DONE!!






