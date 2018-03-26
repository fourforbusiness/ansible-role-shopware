# Ansible Role: ffb Shopware

Role for Shopware-Development on the target machine

## Installed Software

This role will install and prepare the target machine for the installation of shopware.
It is also capable of installing the latest shopware from [shopware.com](https://www.shopware.com).
Additionally it will automatically import databases and copy over files to the target machine if needed. 

## Requirements

Ubuntu with minimum Version 16.04

## Role Variables

    install_project_data: false

This variable defines if project specific data should be imported via the roles `ffb.copy-files` and ffb.`sql-prepare-db`

    setup_shopware: false
    
When this is set to true, the role will install and setup a fresh demo installation of the latest version of shopware.

## Dependencies

### Galaxy-Roles
- [staenker.timezone](https://galaxy.ansible.com/staenker/timezone/)
- [gantsign.oh-my-zsh](https://galaxy.ansible.com/gantsign/oh-my-zsh/)
- [geerlingguy.apache](https://galaxy.ansible.com/geerlingguy/apache/)
- [geerlingguy.php-versions](https://galaxy.ansible.com/geerlingguy/php-versions/)
- [geerlingguy.php](https://galaxy.ansible.com/geerlingguy/php/)
- [geerlingguy.php-mysql](https://galaxy.ansible.com/geerlingguy/php-mysql/)
- [geerlingguy.apache-php-fpm](https://galaxy.ansible.com/geerlingguy/apache-php-fpm/)
- [geerlingguy.mysql](https://galaxy.ansible.com/geerlingguy/mysql/)
- [geerlingguy.php-xdebug](https://galaxy.ansible.com/geerlingguy/php-xdebug/)
- [Akman.ioncube-loader](https://galaxy.ansible.com/Akman/ioncube-loader/)
- [geerlingguy.composer](https://galaxy.ansible.com/geerlingguy/composer/)
- [geerlingguy.nodejs](https://galaxy.ansible.com/geerlingguy/nodejs/)
- [fourforbusiness.copy-files](https://github.com/fourforbusiness/ansible-role-copy-files)
- [fourforbusiness.dev-lamp](https://github.com/fourforbusiness/ansible-role-dev-lamp)
- [fourforbusiness.ansible-basic-setup](https://github.com/fourforbusiness/ansible-role-basic-setup)
- [fourforbusiness.mysql-prepare-db](https://github.com/fourforbusiness/ansible-role-mysql-prepare-db)

## Example Playbook

    ---
    - hosts: all
      become: true
      vars:
        project_tag: 'shopware-role'
        install_project_data: true
        setup_shopware: true
      roles:
        - fourforbusiness.shopware

## License

MIT / BSD

## Author Information

This role was created in 2018 by [four for business AG](https://www.4fb.de/).