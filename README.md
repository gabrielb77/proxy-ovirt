# proxy-ovirt

## Install hosted engine (HE) ovirt 4.4 behind proxy server

a) Edit add_proxy_yum.yml with your setup

b) Copy yml (add_proxy_yum.yml) file to /usr/share/ansible/collections/ansible_collections/ovirt/ovirt/roles/hosted_engine_setup/hooks/enginevm_before_engine_setup/

c) Launch:
```bash
hosted-engine --deploy
```
or
```bash
hosted-engine --deploy --config-append=/path/to/answer/file.conf
```

*If you don't have direct access to an http forward proxy, but ssh, you can setup an ssh tunnel (port forward) like this:

ssh -f -g -N -L ${local-ip-addr}:${local-port}:${proxy-ip-addr}:${proxy-port} ${remote-host-with-proxy-access}

```bash
ssh -f -g -N -L *:80:192.168.0.10:80 192.168.0.10
```

-f: Go backgroung

-g: Allows remote hosts to connect to local forwarded ports.

-N: Do not execute a remote command.  This is useful for just forwarding ports.

-L: Port forwardings (tunnel)


If install fails, you can check with:

```bash
virsh console HostedEngineLocal
```

login with root and test with curl and dnf proxy access.
