Gin
===

Install the [gin scientific data sharing service](https://github.com/G-Node/gogs) using docker.


Role Variables
--------------


Variable | Default | Notes |
-------- | ------- | ----------- |
gin_app_name | - | Required: a human-readable name such as `My GIN`. |
gin_domain | - | Required: a fully-qualified domain name to use for links etc. |
gin_admin_username | - | Required: the user name of the first administrative user. Don't use `admin`. |
gin_admin_password | - | Required: the initial password of the first administrative user. |
gin_admin_email | - | Required: the email address of the first administrative user. |
gin_postgres_password | - | Required: a random password used internally as a shared secret. |
gin_ssh_port | 2121 | Port number used *on the host* |
gin_http_port | 80 | Port number used *on the host* |
gin_enable_federated_avatar | true | |
gin_session_cookie_name | gin_at_home | Change this to improve interoperability if using several gin instances |
gin_login_remember_days | 30 | |
gin_upload_allowed_types | "" | |
gin_upload_file_max_size_MB | 10000 | |
gin_upload_annex_file_min_size_MB | 10 | |
gin_upload_max_files | 100 | |
gin_register_email_confirm | false | |
gin_disable_registration | false | |
gin_require_signin_view | false | |
gin_enable_notify_mail | true | |
gin_enable_captcha | true | |
gin_mailer_enabled | false | |
gin_mailer_host | "" | |
gin_mailer_skip_verify | false | |
gin_mailer_user_certificate | false | |
gin_mailer_from | "" | |
gin_mailer_user | "" | |
gin_mailer_passwd | "" | |
gin_mailer_use_plain_text | false | |
gin_api_max_response_items | 10000 | |
gin_ui_theme_color_meta_tag | "#ffffff" | |
gin_max_git_diff_lines | 1000 | |
gin_max_git_diff_line_characters | 5000 | |
gin_max_git_diff_files | 100 | |
gin_disable_http_git | false | |
gin_show_http_git | false | |
gin_preferred_licenses | "Creative Commons CC0 1.0 Public Domain Dedication" | |
gin_repository_force_private | true | |
gin_repository_auto_init | true | |
gin_public_files | public | Uses the files in `./files/public` by default, but you can copy and customize the folder to change the favicon or CSS. |

Dependencies
------------

This role requires the `community.general` and `community.docker` collections.

Example Playbook
----------------

A fairly minimal playbook to install gin at gin.example.com and switch off registration and notification mails would be:

    - hosts: my-gin-server
      roles:
        - gin
      vars:
        gin_app_name: My gin
        gin_domain: gin.example.com
        gin_admin_username: exampleadmin
        gin_admin_password: 2i3wnv764w5rfv
        gin_admin_email: admin@example.com
        gin_postgres_password: zgvjiermkjfdas
        gin_session_cookie_name: gin_at_example
        gin_disable_registration: true
        gin_enable_notify_mail: false

License
-------

Apache 2.0
