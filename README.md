# smtp_deployment
Kubernetes deployment for simple SMTP server for sending Emails.

This is based on the top of work done by https://github.com/BytemarkHosting/docker-smtp

SMTP deployment can be orchestrated using Kubernetes.

The default yaml files exposes SMTP server as NodePort service on 30050 port.

Environment variables can be passed which defaults to 
    
environment:
  RELAY_HOST: smtp.example.com
  RELAY_PORT: 587
  RELAY_USERNAME: alice@example.com
  RELAY_PASSWORD: secretpassword
