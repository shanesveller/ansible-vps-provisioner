ansible-vps-provisioner
=======================

Ansible playbook with mostly-custom roles for deploying a VPS the way I prefer for personal hosting with nginx/passenger

This collection of ansible roles was partially written by me and occcasionally borrowed wholesale where existing code fits my needs.

This was created by exporting my working copy and purging it of non-general information.

Use `ansible-playbook -i pre-production ssh.yml` to change a stock server to a non-standard SSH port, then update the `production` inventory accordingly.

Use `ansible-playbook -i vps.yml` to deploy the following:

- `deploy` user account
- Ruby 2.1.0
- Java (OpenJDK 7)
- Passenger/nginx from [official APT repo](http://blog.phusion.nl/2013/09/11/debian-and-ubuntu-packages-for-phusion-passenger/)
- [Docker](http://www.docker.io/)
- [Mumble](http://mumble.sourceforge.net/) VoIP server
