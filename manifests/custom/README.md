# Deploying P-RabbitMQ on OpenStack

## Example

```
bosh -e spacex -d p-rabbitmq deploy /opt/spacex/workspaces/cf-rabbitmq-release/manifests/custom/p-rabbitmq-deployment.yml \
    --vars-store /opt/spacex/workspaces/p-rabbitmq-vars.yml \
    -v system_domain=<DOMAIN> \
    -v rabbitmq_haproxy_public_ip=<RABBITMQ_HAPROXY_PUBLIC_IP> \
    --var-file bosh_ca_cert=<BOSH_CA_CERT_FILE> \
    -v uaa_clients_wise_rabbitmq_secret=`bosh int /opt/spacex/creds.yml --path /uaa_clients_wise_rabbitmq_secret` \
    -v uaa_clients_cf_bosh_secret=`bosh int /opt/spacex/workspaces/cf-vars.yml --path /uaa_clients_cf_bosh_secret` \
    -v uaa_clients_cf_admin_secret=`bosh int /opt/spacex/workspaces/cf-vars.yml --path /uaa_clients_cf_admin_secret`
```


