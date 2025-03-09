# Ansible Roles Collection

This repository contains a collection of Ansible roles for installing and configuring various infrastructure components, databases, monitoring tools, and logging solutions.

## 📌 Roles Overview

| Name                | Type  | Description                                      |
|---------------------|-------|--------------------------------------------------|
| `fluentd`           | role  | Ansible role for installing and configuring Fluentd |
| `milvusdb`          | role  | Ansible role for installing and configuring MilvusDB |
| `redis6_primary`    | role  | Ansible role for installing and configuring Redis 6 Primary |
| `telegraf_exporter` | role  | Ansible role for installing and configuring Telegraf Exporter |
| `docker`            | role  | Ansible role for installing and configuring Docker |
| `prometheus`        | role  | Ansible role for installing and configuring Prometheus |
| `redis6_replica`    | role  | Ansible role for installing and configuring Redis 6 Replica |
| `kafka_broker`      | role  | Ansible role for installing and configuring Kafka Broker |
| `fluentbit`         | role  | Ansible role for installing and configuring Fluent Bit |
| `kibana`            | role  | Ansible role for installing and configuring Kibana |
| `telegraf_gateway`  | role  | Ansible role for installing and configuring Telegraf Gateway |
| `elasticsearch`     | role  | Ansible role for installing and configuring Elasticsearch |
| `node_exporter`     | role  | Ansible role for installing and configuring Node Exporter |
| `linux_ops_tools`   | role  | Ansible role for installing common Linux operations tools |
| `grafana`           | role  | Ansible role for installing and configuring Grafana |

## 🚀 Usage
Each role is designed to be reusable and configurable. To use a role in your Ansible playbook, include it as follows:

```yaml
- hosts: target_hosts
  roles:
    - role: docker
    - role: prometheus
    - role: redis6_primary
```

### 🔧 Role Variables
Each role may contain configurable variables. Refer to the specific role's `defaults/main.yml` or `README.md` for available options.

## 📂 Repository Structure
```
ansible-roles-repo/
├── roles/
│   ├── fluentd/
│   ├── milvusdb/
│   ├── redis6_primary/
│   ├── telegraf_exporter/
│   ├── docker/
│   ├── prometheus/
│   ├── redis6_replica/
│   ├── kafka_broker/
│   ├── fluentbit/
│   ├── kibana/
│   ├── telegraf_gateway/
│   ├── elasticsearch/
│   ├── node_exporter/
│   ├── linux_ops_tools/
│   ├── grafana/
│
└── playbooks/
```

## 📢 Contributing
Feel free to open issues or submit pull requests if you'd like to improve or extend the roles in this repository.

## 📜 License
This project is licensed under the [MIT License](LICENSE).

---
Maintained by **Your Team/Organization**

