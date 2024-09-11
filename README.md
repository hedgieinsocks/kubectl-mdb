# kubectl-mdb

`kubectl-mdb` is a simple `kubectl` plugin that helps interact with [mariadb-operator](https://github.com/mariadb-operator) semi-sync replication clusters.

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
kubectl mdb helps interact with mariadb-operator semi-sync replication clusters

Usage:
  kubectl mdb <command>

Available Commands:
  list|ls                    list mariadbs and pods
  status|st <mariadb>        show mariadb status
  enter|ent <pod>            enter a mariadb pod
  mysql|sql <pod>            launch mysql shell
  proc|pr <pod>              show mysql processlist
  disk|du <pod>              calculate database disk usage
  repl|rpl <replica>         check replication status
  trans|tr <replica>         skip errant transactions
  promote|prom <replica>     promote replica to primary

Flags:
  -n, --namespace string     set namespace scope
  -v, --version              show plugin version
  -h, --help                 show this message
```
