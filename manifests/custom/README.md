# Deploying P-RabbitMQ on OpenStack

## Example

```
bosh -e spacex -d p-rabbitmq deploy /opt/spacex/workspaces/cf-rabbitmq-release/manifests/custom/p-rabbitmq-deployment.yml \
    --vars-store /opt/spacex/workspaces/p-rabbitmq-vars.yml \
    -v system_domain=<DOMAIN> \
    -v rabbitmq_haproxy_public_ip=`bosh int /opt/spacex/tf/terraform-vars.yml --path /rabbitmq_haproxy_public_ip` \
    --var-file bosh_ca_cert=/opt/spacex/bosh_ca_cert \
    -v uaa_clients_wise_rabbitmq_secret=`bosh int /opt/spacex/creds.yml --path /uaa_clients_wise_rabbitmq_secret` \
    -v uaa_users_cf_bosh_password=`bosh int /opt/spacex/workspaces/cf-vars.yml --path /cf_bosh_password` \
    -v uaa_users_cf_admin_password=`bosh int /opt/spacex/workspaces/cf-vars.yml --path /cf_admin_password`
```


