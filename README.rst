Odoo installation playbook
~~~~~~~~~~~~~~~~~~~~~~~~~~

**This playbook takes care of the following:**

- Odoo
- Postgresql
- NGINX
- SSL certificate (Let's Encrypt)
- UFW
- Fail2ban
- Automatic backup of database and filestore using autopostgresqlbackup

**Prerequisites:**

* Ansible (https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
* An Ubuntu 20.04 machine

**Parameters:**

- **domain** (*optional*): e.g. odoo.mycompany.com certbot needs this to get a certificate
- **email** (*optional*): Used for notifications about your SSL certificate and backups
- **target**: Target in Ansible hosts file

**How to use:**

.. code-block::

    git clone git@github.com:onesteinbv/ansible-playbooks.git onestein-ansible-playbooks
    cd onestein-ansible-playbooks
    ansible-playbook install_odoo_playbook.yml -e target=odoo-vm -e domain=odoo.mycompany.com -e email=info@mycompany.com
