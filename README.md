# ela-bootstrap
## Install fresh ELA node
1. ```shell
    sudo apt-get install -y jq apache2-utils
    ```
2. Follow https://elastos.dev/nodes/quick-setup/

## Resync from boostrap
1. ```shell
   ~/node/node.sh ela stop
   ```
2. ```shell
   mkdir ~/bootstrap && cd ~/bootstrap
   ```
3. To enable the download, please contact @MButcho via Elastos Discord or Telegram
   ```shell
   wget https://node.elasafe.com/data.tar.gz
   ```
4. ```shell
   tar -xvf data.tar.gz
   ```
5. ```shell
   mv ~/node/ela/elastos/data ~/node/ela/elastos/data_old
   ```
6. ```shell
   mv  ~/bootstrap/data/ ~/node/ela/elastos/data
   ```
7. ```shell
   ~/node/node.sh ela start
   ```

## Once synced to latest height and your node is Inactive:
1. ```shell
   ~/node/node.sh ela activate_dpos
   ```
2. If you have error with existing files ready_to_send.txn and/or to_be_signed
    ```shell
    rm ~/node/ela/ready_to_send.txn && rm ~/node/ela/to_be_signed.txn
    ```
3. Copy last tx hash and check tx on https://ela.elastos.io/ 
4. In 5 confirmations, your node should be active

## After few days, when you node is running OK, you can clean up:
1. ```shell
   rm -rf ~/bootstrap
   ```
2. ```shell
   rm -rf ~/node/ela/elastos/data_old
   ```
3. ```shell
   rm ~/node/ela/ready_to_send.txn
   ```
4. ```shell
   rm ~/node/ela/to_be_signed.txn
   ```

## Create your own bootstrap

_Remember, the node must be working correctly_

1. ```shell
   ~/node/node.sh ela stop
   ```
2. ```shell
   cd ~/node/ela/elastos
   ```
3. ```shell
   tar -czvf data.tar.gz data
   ```
4. ```shell
   ~/node/node.sh ela start
   ```
5. Your boostrap is available in ~/node/ela/elastos/data.tar.gz

# Donations

Any donation to BTC LN address **tipme@walletofsatoshi.com** or ELA address **EJfW2mCdZPVxHVEv891xDop7hJAsYbKH5R** will be appreciated.

### Thank you and enjoy!