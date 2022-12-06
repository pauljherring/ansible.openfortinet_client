openfortivpn
=========

Ensures `openfortivpn` is installed, configured and runs on reboot. Will restart tunnel if it dies.

Output is sent to `/var/log/openfortivpn`, which is rotated daily with the last 7 days saved.

Requirements
------------

Role Variables
--------------

`defaults/main.yml`

- `openfortivpn_user`: VPN user name
- `openfortivpn_pass`: VPN Password
- `openfortivpn_trusted_cert`: Trusted cert for the VPN server
- `openfortinet_host`: Name/IP address of the VPN server
- `openfortinet_port`: Port to contact the VPN server on

- `openfortinet_routes`: Which routes (in `IP/mask` format) to route over the VPN. Defaults to `10.0.0.0/8` plus `172.16.0.0/12` except `172.17.0.0/16` to allow space for things like docker. (See `defaults/main.yml` for more details.)

`vars/main.yml`

- `openfortivpn_package`: Package name to install (`openfortivpn`)
- `openfortivpn_version`: Version to install (not currently used - `1.17.1`)
- `openfortinet_dir`: Configuration directory (`/etc/openfortivpn`)

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT

Author Information
------------------
