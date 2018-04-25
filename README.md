# Daemon
```bash
docker run --name GraftDaemon --volume daemon:/daemon/data easyhash/graft:latest /daemon/graftnoded --log-level=0 --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18081 --data-dir=/daemon/data --confirm-external-bind
```

# Wallet
```bash
docker run --name GraftWallet --volume wallet:/daemon/data --link GraftDaemon:daemon easyhash/graft:latest /daemon/graft-wallet-rpc --daemon-address=http://daemon:18081 --wallet-file=/daemon/data/graft.wallet --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18082 --confirm-external-bind --trusted-daemon --disable-rpc-login --password '<wallet password>' --log-level=0
```