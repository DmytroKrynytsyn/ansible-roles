Kafka Broker
=========

This role configures a Kafka broker as part of a Kafka cluster, handling installation, configuration, and initialization required for each broker in a distributed Kafka setup.

Requirements
------------

This role requires:

Any prerequisites not covered by Ansible itself or this role should be mentioned here. For example:

- The system must be Linux-based (tested on Ubuntu and CentOS).
- Root or sudo privileges are required to install and configure Kafka.
- Java must be installed on the system; either provide the path to an existing Java installation or set up a role to handle Java installation.

Role Variables
--------------

A description of the configurable variables for this role is provided here, including any variables in defaults/main.yml, vars/main.yml, or variables that can be passed in via parameters to the role. Variables that are retrieved from other roles or from the global scope (e.g., hostvars, group vars, etc.) should also be mentioned.

- Basic Configuration
-- kafka_version: The version of Kafka to install (default: latest).
-- kafka_broker_id: Unique identifier for the broker within the cluster (e.g., 0, 1, 2).
-- kafka_port: The port on which Kafka will listen (default: 9092).
-- kafka_log_dirs: Directories where Kafka will store log files (default: /var/lib/kafka/data).

- Cluster Configuration
-- zookeeper_connect: List of Zookeeper hosts used for Kafka cluster coordination (e.g., ["zk1:2181", "zk2:2181", "zk3:2181"]).
-- kafka_auto_create_topics_enable: Whether to enable automatic creation of topics (default: true).
-- kafka_num_partitions: Default number of partitions per topic (default: 1).
kafka_default_replication_factor: Default replication factor for topics (default: 1).
- Security Configuration
-- kafka_ssl_enabled: Enables SSL encryption for broker communications (default: false).
-- kafka_sasl_mechanism: SASL mechanism for client authentication (e.g., PLAIN, SCRAM-SHA-256).
-- kafka_client_auth: Whether to require client authentication if SSL is enabled (default: required).
-- kafka_broker_password: Password for broker authentication if SASL/SSL is enabled.

Dependencies
------------

List any other roles hosted on Galaxy or required by this role. For instance, a role for setting up Java may be needed, or other roles that provide dependencies required for running Kafka.


Example Playbook
----------------

Including an example of how to use this role, including any variables passed in as parameters, can be helpful for users:
- hosts: kafka_brokers
  become: true
  vars:
    kafka_version: "2.8.1"
    kafka_broker_id: 1
    kafka_port: 9092
    kafka_log_dirs: "/data/kafka/logs"
    zookeeper_connect:
      - "zk1:2181"
      - "zk2:2181"
      - "zk3:2181"
    kafka_auto_create_topics_enable: true
    kafka_num_partitions: 3
    kafka_default_replication_factor: 2
    kafka_ssl_enabled: true
    kafka_sasl_mechanism: "SCRAM-SHA-256"
    kafka_broker_password: "my_secure_password"
  roles:
    - { role: dmytrokrynytsyn.components.kafka_broker }


License
-------

BSD

Author Information
------------------

This role is maintained by the Ansible community, with contributions from Dmytro Krynytsyn. For any queries or contributions, please reach out via the GitHub repository.
