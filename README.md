# kubectl-mdb

`kubectl-mdb` is a simple `kubectl` plugin that helps interact with [mariadb-operator](https://github.com/mariadb-operator) 2-replica semi-sync clusters.

_This project is not affiliated with MariaDB._

## Dependencies

* `jq` - https://github.com/jqlang/jq
* `yq` - https://github.com/kislyuk/yq

## Installation

Place `kubectl-mdb` into the directory within your `PATH` (e.g. `~/.local/bin` or `~/.krew/bin`)

## Customization

You can export the following variables to tweak the plugin's behaviour.

| VARIABLE         | DEFAULT   | DETAILS                            |
|------------------|-----------|------------------------------------|
| `KMDB_NAMESPACE` | `default` | default k8s namespace              |

## Usage

```
kubectl mdb helps interact with mariadb-operator 2-replica semi-sync clusters

Usage:
  kubectl mdb <command> <arg> [-n <string>] [-h]

Available Commands:
  list|ls                    list clusters and pods

  enter|ent <pod>            enter a mariadb pod
  mysql|sql <pod>            launch mysql shell
  proc|pr <pod>              show mysql processlist
  disk|du <pod>              show database disk usage

  status|st <mariadb>        show cluster status
  repl|rpl <mariadb>         check slave replication
  trans|tr <mariadb>         skip errant transactions
  failover|fail <mariadb>    trigger master failover

Flags:
  -n, --namespace string     set namespace scope
  -h, --help                 show this message
```
