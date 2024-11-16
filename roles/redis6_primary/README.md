Redis Cluster Node Role
=========

This role configures a Redis node as part of a Redis cluster. It handles the installation, configuration, and initialization necessary for a node to participate in a Redis cluster.

Requirements
------------

This role requires:

- A Linux-based system (tested on Ubuntu and CentOS).
- Root or sudo privileges to install and configure Redis.
- Redis binary files available in the system's package manager, or download paths for custom installations.

Role Variables
--------------

The following variables can be configured to customize the role's behavior. They can be set in defaults/main.yml or overridden in playbooks or inventory files:

- Basic Configuration
-- redis_version: Version of Redis to install (default: latest).
-- redis_bind_address: Address on which Redis will listen (default: 0.0.0.0).
-- redis_port: Port on which Redis will listen (default: 6379).
- Cluster-Specific Configuration
-- redis_cluster_enabled: Whether to enable Redis clustering (default: true).
-- redis_cluster_node_timeout: Timeout in milliseconds for node-to-node communication (default: 5000).
-- redis_cluster_replicas: Number of replicas to assign to each master node (default: 1).
- Security Configuration
-- redis_password: Password for Redis authentication. If not set, no password is used.
-- redis_requirepass: Whether Redis should require a password to connect (default: false).


Dependencies
------------

This role does not have direct dependencies but may benefit from a base role that installs common dependencies (e.g., geerlingguy.redis). Ensure any required roles are listed in requirements.yml if this is part of an automated build.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- hosts: redis_nodes
  become: true
  vars:
    redis_version: "6.2.6"
    redis_bind_address: "0.0.0.0"
    redis_port: 6379
    redis_cluster_enabled: true
    redis_cluster_node_timeout: 5000
    redis_cluster_replicas: 1

  roles:
    - { role: dmytrokrynytsyn.components.redis_node }


License
-------

BSD

Author Information
------------------

This role is maintained by the Ansible community, with contributions from Dmytro Krynytsyn. For any queries or contributions, please reach out via the GitHub repository.
