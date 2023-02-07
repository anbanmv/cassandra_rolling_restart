# cassandra_rolling_restart
Ansible playbook to restart nodes in Cassandra cluster in rolling fashion.

# How to executue:
ansible-playbook playbook_rolling_restart.yml -i inventory

# Tasks performed by the playbook:
1. Validates if all nodes in cluster are healthy.
2. Validates if backup is in progress.
3. Disables thrift.
4. Disables native transport.
5. Disables gossip.
6. Flushes data from memtables to SSTables.
7. Restarts Cassandra service.
8. Waits until the service is back online before proceeding with next node in cluster.
