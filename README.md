openssh-git
===========

  This is a fork of openssh 6.4p1 that also passes the public key as the second argument
to AuthorizedKeysCommand.

Danger
======

  This probably isn't safe and you probably shouldn't use it.

How to use
==========

  Follow the instructions for how to use the AuthorizedKeyCommand.  
  
  Generally, what I do is, if the key passed in is authorized, I'll print 
something like the following to standardOut

```shell
echo "command='/usr/local/bin/my-script $username',no-port-forwarding,no-X11-forwarding,no-agent-forwarding,no-pty ssh-rsa $pubkey"
```

Where `$username` is the user from your database associated with the key,
and `$pubkey` is just `$2` (the second argument to the command)

If no users match, then just don't print anything to standardOut.
