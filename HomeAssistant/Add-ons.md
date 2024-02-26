# Add-ons

## Advanced SSH & Web Terminal

Remember to change: username & authorized_keys and no password, then it only the pc with the corect ssh key that have access, you can have more keys.

```code
username: hassio
password: ""
authorized_keys:
  - >-
    ssh-ed25519
    asdspaaspdadsasdasdfasdfasdfasdfafsdf/
    abekat@gmail.com
  - >-
    ssh-ed25519
    asdspaasdasdhjkghghjghjjghjkgukfafsdf/
    hunkat@gmail.com
sftp: false
compatibility_mode: false
allow_agent_forwarding: false
allow_remote_port_forwarding: false
allow_tcp_forwarding: false
```
