# Gitea

Install and configure Gitea, a self-hosted git-frontend on a machine running
Debian GNU/Linux.

Note: SQLite3 is the only backend supported by this role as of now. This has
only been tested on Debian `Bullseye` and AMD64. It's likely to work with older
/ newer versions of Debian too, as well as with Debian-derivatives such as
Ubuntu. However this has not been confirmed.

#### Variables

Variables can be configured in `vars/main.yml`, otherwise the defaults defined
in `defaults/main.yml` will be used when run. It is *highly* recommended to
change the defaults in an environment that is not an isolated testing
environment.

```
# General
gitea_version: # Gitea-version to be downloaded, must be found at https://dl.gitea.io/gitea
gitea_user: gitea # System-user Gitea will run under

# Gitea
app_name: # Title of the instance
internal_token: # Secret used to validate communication with Gitea-binary, random string
secret_key: # Global secret key, random string
lfw_jwt_secret: # LFS authentication secret, random string
ssh_domain: # The domain to be used for the ssh-connections
web_domain: # The domain to be used for the webinterface

# Users
admin_user: # Username of the first user to be created, who has admin rights
admin_mail: # Mail address of the first user to be created
```

#### Missing features

* Optional support for other database backends
* OAuth-Integration
* Mailer-configuration
* Automatic creation of admin-user (currently failing)
* Whitelist for Web-Hooks
