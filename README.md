# This base was designed to work with ISU ansible roles collection to install Galera cluster #
- To make it work for general machines Please change the following
-- Firewall settings such that each node can talk to each other. The mysql port avaliable from the nodes to attach to clients.
-- Place certs if you are using ssl in files mysql_certs
-- If no certs used change mysqld settings

# Install and configure a Maria BD Galera cluster #

## Currently using mariaDB Galera Repo for maria db 10##
This is a role to configure a mariadb galera cluster. The group name for the cluster is set up as galera and the role will will use the first host from galera group as the primary machine to set up galera wsrep set up.

This is beacuse although galera does not have a master slave set up you have to define the first server to which other nodes replicate to during initial setup.

## Restrictions
- We are assuming that you are using RHEL 6/7

## Variables
- galera_packages : Contain all packages necessary for galera setup
- galera_cluster_name : Name givin to galera cluster [Default: MariaDB_Cluster]
