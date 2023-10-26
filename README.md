# OAuth2 Proxy with Keycloak Deployment on Kubernetes

This repository contains Kubernetes deployment manifests for setting up OAuth2 Proxy and Keycloak for secure and efficient authentication and authorization.

## Overview

OAuth2 Proxy is a reverse proxy and static file server that provides authentication using different providers, including Keycloak. It allows you to protect your web applications and APIs easily. This repository demonstrates how to deploy OAuth2 Proxy with Keycloak on a Kubernetes cluster using Kustomize.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

- Kubernetes cluster configured and running.
- `kubectl` command-line tool installed and configured to access your cluster.
- [Kustomize](https://kubectl.docs.kubernetes.io/pages/app_management/introducing_kustomize.html) installed.

## Deployment

To deploy OAuth2 Proxy with Keycloak, follow these steps:

1. Clone this repository:

   ```bash
   git clone https://github.com/ahmadzana/oauth2proxy-keycloak.git
   cd #oauth2proxy-keycloak

2. configure the following environment variables for your Keycloak deployment. These variables are typically stored in a `.env` file located in the `keycloak/` directory:


# KeyCloak
```
KC_DB: Specifies the database type used by Keycloak (in this case, PostgreSQL).
KC_DB_PASSWORD: The password for the Keycloak database.
KC_DB_URL: The JDBC URL for connecting to the PostgreSQL database.
KC_DB_URL_PORT: The port number for the database.
KC_DB_USERNAME: The username for the Keycloak database.
KC_HOSTNAME: The hostname for Keycloak (ingress-hostname).
KC_PROXY: The proxy configuration for Keycloak.
KEYCLOAK_ADMIN: The Keycloak admin username.
KEYCLOAK_ADMIN_PASSWORD: The admin password for Keycloak.
POSTGRESQL_USERNAME: The PostgreSQL username.
POSTGRESQL_DATABASE: The PostgreSQL database name.
POSTGRESQL_PASSWORD: The password for the PostgreSQL database.
DATABASE__PORT: The port number for the PostgreSQL database.

```
3. Deploy the resources:

Use kubectl and Kustomize to apply the deployment:
```bash
kustomize build | kubectl apply -f -
```
