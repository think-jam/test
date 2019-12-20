<!-- TITLE: Ssh Keys -->
<!-- SUBTITLE: A quick summary of Ssh Keys -->

# SSH keys

This article shows you how to create an SSH key and how to add it to a Think Jam server for use in deployment

## Creating an SSH key

open terminal and type the following command:


```text
ssh-keygen -t rsa
```

Leave everything default and **make sure you leave the password empty**

Next, type the following to copy the key to your clipboard:

```text
pbcopy < ~/.ssh/id_rsa.pub
```


Paste this into a file and pass to the Lead Developer to assign to the right servers.

If you are using Digital Ocean, you should use one login and assign your key in the security settings there.











