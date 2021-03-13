# proxy-ovirt

Install hosted engine (HE) ovirt 4.4 behind proxy server

Edit add_proxy_yum.yml with your setup
Copy yml (add_proxy_yum.yml) file to /usr/share/ansible/collections/ansible_collections/ovirt/ovirt/roles/hosted_engine_setup/hooks/enginevm_before_engine_setup/

Launch hosted-engine --deploy or hosted-engine --deploy --config-append=/path/to/answer/file.conf

