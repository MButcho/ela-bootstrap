# ela-bootstrap
## Install fresh ELA node
1. sudo apt-get install -y jq apache2-utils
2. Follow https://elastos.dev/nodes/quick-setup/

## Resync from boostrap
1. ~/node/node.sh ela stop
2. mkdir ~/bootstrap && cd ~/bootstrap 
3. wget https://ela.nodes.sk/node.tar.gz (to enable you to download, please contact @MButcho via Elastos Discord or Telegram
4. tar -xvf node.tar.gz
5. mv ~/node/ela/elastos/data ~/node/ela/elastos/data_old
6. mv  ~/bootstrap/node/ela/elastos/data/ ~/node/ela/elastos/data
7. ~/node/node.sh ela start

## Once synced to latest height and your node is Inactive:
1. ~/node/node.sh ela activate_dpos
2. If you have error with existing files ready_to_send.txn and/or to_be_signed
    rm ~/node/ela/ready_to_send.txn
    rm ~/node/ela/to_be_signed.txn
3. Copy last tx hash and check tx on https://ela.elastos.io/ 
4. In 5 confirmations, your node should be active

## After few days, when you node is running OK, you can clean up:
1. rm -rf ~/bootstrap
2. rm -rf ~/node/ela/elastos/data_old
3. rm ~/node/ela/ready_to_send.txn
4. rm ~/node/ela/to_be_signed.txn
