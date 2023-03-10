server-apps
=========

Ansible galaxy role for server apps & configs

Role Variables
--------------

## Common

* git_user --> git account name
* volumes_folder --> where to link the docker volumes folder
* dockers --> Array with the list of dockers. Example: `dockers: ["jellyfin","gitea"]`
* ip_whitelist --> Ip or range for whitelisting.
* ansible_ext --> Where to get ansible extra resources
* selfsigned_certs --> Array with the names of the selfsigned certs. Example: `selfsigned_certs["domain-selfsig.crt","domain-selfsig.key"]`
* domain --> domain name
* ext_drives --> external drives folders
* user_uid --> *1
* user_gid --> *1
* user --> Username for the installation user
* group --> Group name for the user

## Syncthing
* syncthing_subdomain --> subdomain name
* syncthing_port --> Port number

## SSL
* ssl_certificate --> ssl crt file full path
* ssl_certificate_key --> ssl key file full path

## Gitea
* gitea_db_name --> database name 
* gitea_db_user --> database user 
* gitea_db_pass --> database password
* gitea_port --> port number
* gitea_ssh_port --> ssh port number
* gitea_subdomain --> subdomain name

### Jellyfin
jellyfin_subdomain --> subdomain name
jellyfin_port --> port number
jellyfin_url --> full jellyfin url. Example: https://jellyfin.your.domain
jellyfin_movies --> movies folder
jellyfin_shows --> shows foler
jellyfin_comics --> comics folder
jellyfin_music --> music folder

*1 From the playbook
`- name: Variable for uid
  command: "id -u {{ user }}"
  register: uid_command

- name: Set user_uid var
  set_fact:
    user_uid: "{{ uid_command.stdout }}"

- name: Variable for gid
  command: "id -g {{ user }}"
  register: gid_command

- name: Set user_gid var
  set_fact:
    user_gid: "{{ gid_command.stdout }}"`

License
-------

Yet to be determined

Author Information
------------------

[Sandstorm](https://github.com/SandstormCG) 
