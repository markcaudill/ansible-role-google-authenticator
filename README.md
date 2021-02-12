google_authenticator
====================

Configure a Linux host to use Google Authenticator/TOTP

Requirements
------------

Hosts should have access to the EPEL repository or some other way to use the built-in package manager to install the `google-authenticator` and optionally, `qrencode-libs` packages.

Role Variables
--------------

`google_authenticator_packages` is a list of packages to install and must at least include `google-authenticator` or some other package that provides the `google-authenticator` command and PAM module. By default `qrencode-libs` is installed as well to allow an ANSI QR code to be shown in the terminal.

`google_authenticator_pam_configurations` is a list of PAM configurations. By default it configures the `su` PAM module to require an authentication token if the target account has 2FA configured (i.e. `$HOME/.google_authenticator` exists).

Dependencies
------------

- `geerlingguy.repo-epel`

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: markcaudill.google_authenticator }

License
-------

MIT

Author Information
------------------

Mark Caudill <mark@mrkc.me>
