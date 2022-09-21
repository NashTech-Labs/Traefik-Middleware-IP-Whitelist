# IP Whitelist

IP whitelisting will allow you to create lists of IP addresses or IP ranges from which your users can access your domains. It provides a security feature often used for controlling and limiting access only to trusted users.

# Update External Traffik Policy

To whitelist IPs first we need to patch the traefik Ingress Controller service.Use below command to patch the service.

`kubectl patch service traefik -n kube-system --patch $'spec:\n externalTrafficPolicy: local\n'`

# ADD Ips that need to be whitelist

Add the IPs that need to be Whitelist in `middleware.yaml` file under the `sourceRange` section

# Apply all the yaml file using kubectl command

`kubectl apply -f <file_name>`