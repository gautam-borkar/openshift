# Openshift

## Openshift commands 
### Login
`oc login`

### Token 
**Session Tokens** A session token is short-lived, expiring within 24 hours by default. It represents a user. After logging in, the session token may be obtained with the oc whoami command:

`oc whoami --show-token=true`

**Service Account Tokens** A service account tokens are long-lived tokens. They are JSON Web Token (JWT) formatted tokens and are much longer strings than session tokens. A service account token may be obtained with these commands:

Create a service account in the current project named robot:
```
oc create serviceaccount robot
oc policy add-role-to-user admin system:serviceaccount:test:robot
oc serviceaccounts get-token robot
```
