# smtp_deployment
Kubernetes deployment for simple SMTP server for sending Emails.

This is based on the top of work done by https://github.com/BytemarkHosting/docker-smtp

SMTP deployment can be orchestrated using Kubernetes.

The default yaml files exposes SMTP server as NodePort service on 30050 port.

# Deploy

To deploy, clone and CD into this repo

`kubectl apply -f k8manifests`

# Environment variables

Environment defaults to
    
environment:
  RELAY_HOST: smtp.example.com
  RELAY_PORT: 587
  RELAY_USERNAME: alice@example.com
  RELAY_PASSWORD: secretpassword
  
All environment variables are optional. But if you specify a RELAY_HOST, then you'll want to also specify the port, username and password otherwise it's unlikely to work!

MAILNAME: Sets Exim's primary_hostname, which defaults to the hostname of the server.
RELAY_HOST: The remote SMTP server address to use.
RELAY_PORT: The remote SMTP server port to use.
RELAY_USERNAME: The username to authenticate with the remote SMTP server.
RELAY_PASSWORD: The password to authenticate with the remote SMTP server.
RELAY_NETS: Declare which networks can use the smart host, separated by semi-colons. By default, this is set to 10.0.0.0/8;172.16.0.0/12;192.168.0.0/16, which provides a thin layer of protection in case port 25 is accidentally exposed to the public internet (which would make your SMTP container an open relay).
