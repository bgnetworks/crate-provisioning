# crate-provisioning

This repo contains Ansible configuration for provisioning a CRATE computer.

## Installing Dependencies

To set up an environment:

```bash
# create a python virtualenv to work in
virtualenv crate-provisioning-env
# enable the virtualenv
source crate-provisioning-env/bin/activate
# install python dependencies
pip install -r requirements.txt
```

## Provisioning 

To provision a host locally: `TAILSCALE_KEY=key ansible-playbook -K crate_host.yml`

The value of `TAILSCALE_KEY` must be replaced with an API key, which can be obtained from https://login.tailscale.com/admin/settings/keys.

The `-K` flag makes Ansible request the BECOME password from a prompt. You will need to enter your password to allow sudo access when running this script.

To provision without Tailscale (useful for testing): `ansible-playbook -K crate_host.yml --skip-tags tailscale`

