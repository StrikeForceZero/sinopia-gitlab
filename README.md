# sinopia-gitlab

Sinopia plugin for Gitlab authentication and package access/publish authorization.

This plugin allows authentication to Sinopia using a gitlab username and password.  It also checks access levels
for users and projects before allowing access to project code (minimum level "Reporter") or publish access
(minimum level "Master").

## Configuration

````
auth:
  gitlab:
    gitlab_server: https://git.example.com
    gitlab_admin_private_token: MyPrivateToken # You can use private token here
    #gitlab_admin_username: admin              # or provide usernam and password (not recommended)
    #gitlab_admin_password: password123
    gitlab_project_prefix: npm-
    gitlab_ca_file: /path/to/ca/ca.crt
    
packages:
  'prefix-*':
    gitlab: true
  '*':
    allow_access: $authenticated
    allow_publish: []
    proxy: npmjs

````
