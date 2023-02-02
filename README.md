# cassandra_rolling_restart
Ansible playbook to restart nodes in Cassandra cluster in rolling fashion.

# How to executue:
ansible-playbook playbook_rolling_restart.yml -i inventory

# Tasks performed by the playbook:
1. Validates if all nodes in cluster are healthy.
2. Disables thrift.
3. Disables native transport.
4. Disables gossip.
5. Flushes data from memtables to SSTables.
6. Restarts Cassandra service.
7. Waits until the service is back online before proceeding with next node in cluster.
