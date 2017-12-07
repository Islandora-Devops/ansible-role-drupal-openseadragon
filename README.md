# Ansible Role: Drupal-OpenSeadragon

An Ansible role that installs the [Drupal 8 field formatter](https://github.com/Islandora-CLAW/openseadragon) and [OpenSeadragon library](https://openseadragon.github.io/) on:

* Centos/RHEL 7.x
* Ubuntu Xenial

## Role Variables

Available variables are listed below, along with default values:

```
# Composer package for openseadragon
openseadragon_composer_item: "islandora/openseadragon:dev-8.x-1.x"
# Root of drupal instance
openseadragon_composer_root: "/var/www/html/drupal"
# Sites to install openseadragon into
openseadragon_sites:
  - default
# Version of openseadragon library
openseadragon_version: 2.2.1
# Temporary directory to download library to.
openseadragon_temp_folder: /tmp
# Check whether there is already a IIIF address registered.
# Default action is to overwrite whatever is there with the
# configured address
openseadragon_iiiv_set_var: false
# Address for your IIIF server
openseadragon_iiiv_server:

```

## Dependencies

* Drupal 8
* Working IIIF image server we recommend
   * Islandora-Devops.cantaloupe
     * [Github](https://github.com/Islandora-DevOps/ansible-role-cantaloupe)
     * [Galaxy](https://galaxy.ansible.com/Islandora-Devops/cantaloupe/)
  
## Example Playbook

    - hosts: webservers
      roles:
        - { role: Islandora-Devops.drupal-openseadragon }

## License

MIT