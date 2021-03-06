#  <img src="https://img.shields.io/static/v1?label=&message=Ansible&color=black" width="100" height="35"/>  Configuration Management (Node Weight Tracker) Staging and Production Environments

![ansible_tree](https://user-images.githubusercontent.com/83014719/139578986-3b2ef820-2d45-4627-9533-6e1ad2a41a00.png)

### Install Ansible
* Run `sudo apt update` and `sudo apt upgrade`
* [Download and install](https://linuxhint.com/begineers_guide_tutorial_ansible/) `ansible` on your linux virtual machine (controller).
* Create ssh key with `ssh-keygen` command.
* Copy the key to the agents by using `ssh-copy-id <path-to-file> user@hostname` command.
* On `.env` creating use variables file for your  `OKTA`,  `PostgreSQL`,  `Hosts`  and other sensitive data.
* Encrypt the variables file by using Ansible vault `sudo ansible-vault encrypt variables.yml` (example).
* To use `ipify_facts` install: `ansible-galaxy collection install community.general`
* Create `vault.yml` file for your secret variables (one for each environment):
* ![vault_example](https://user-images.githubusercontent.com/83014719/139579823-497ea648-c0c9-4fac-bcf9-19e4acf90709.png)
* Check the hosts connection `ansible -i ./ansible/environments/staging/inventory all -u ubuntu -m ping` for staging env.
* Check the hosts connection `ansible -i ./ansible/environments/production/inventory all -u ubuntu -m ping` for production env.
* Run playbook with `ansible-playbook -i ./environments/staging/inventory playbook.yml` command for deployment to staging (while your variables file is decrypted). 
* Run playbook with `ansible-playbook -i ./environments/production/inventory playbook.yml` command for deployment to production (while your variables file is decrypted).

---

![week-6-envs](https://user-images.githubusercontent.com/83014719/138560843-a874c1e8-f789-44f9-8140-42bc55e22d6d.png)
# Node.js Weight Tracker

![build-weight-tracker-app-demo](https://user-images.githubusercontent.com/83014719/137505630-ccf4c3f4-6e06-4778-b414-830d6bb23f99.gif)

This sample application demonstrates the following technologies.

* [hapi](https://hapi.dev) - a wonderful Node.js application framework
* [PostgreSQL](https://www.postgresql.org/) - a popular relational database
* [Postgres](https://github.com/porsager/postgres) - a new PostgreSQL client for Node.js
* [Vue.js](https://vuejs.org/) - a popular front-end library
* [Bulma](https://bulma.io/) - a great CSS framework based on Flexbox
* [EJS](https://ejs.co/) - a great template library for server-side HTML templates

**Requirements:**

* [Node.js](https://nodejs.org/) 12.x or higher
* [PostgreSQL](https://www.postgresql.org/) (can be installed locally using Docker)
* [Free Okta developer account](https://developer.okta.com/) for account registration, login

## Install and Configuration

1. Clone or download source files
1. Run `npm install` to install dependencies
1. If you don't already have PostgreSQL, set up using Docker
1. Create a [free Okta developer account](https://developer.okta.com/) and add a web application for this app
1. Copy `.env.sample` to `.env` and change the `OKTA_*` values to your application
1. Initialize the PostgreSQL database by running `npm run initdb`
1. Run `npm run dev` to start Node.js




