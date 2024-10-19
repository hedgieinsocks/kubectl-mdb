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
  list [<mariadb>]     list mariadbs and pods
  top [<pod>]          display resource usage
  status <mariadb>     show mariadb status
  enter <pod>          enter a mariadb pod
  mysql <pod>          launch mysql shell
  proc <pod>           print mysql processlist
  disk <pod>           calculate database disk usage
  repl <replica>       check replication status
  tran <replica>       skip errant transactions
  prom <replica>       promote replica to primary

Flags:
  -n, --namespace string     set namespace scope
  -v, --version              show plugin version
  -h, --help                 show this message
```
