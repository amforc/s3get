# S3Get

Download a single file from S3 using parallel downloads.

More information on [Parasnaps](https://parasnaps.io/)

## Available Regions

| Region | City | S3 URI |
|--|--|--|
| Europe | Ireland | ```s3://euw1.parasnaps.io/``` |
| Europe | Frankfurt | ```s3://euc1.parasnaps.io/``` |
| US East | N. Virginia | ```s3://use1.parasnaps.io/``` |
| US West | Oregon | ```s3://usw2.parasnaps.io/``` |
| Asia Pacific | Singapore | ```s3://apse1.parasnaps.io/``` |

## Usage Examples

1. Download and extract snapshot
```sh
# s3get s3://<S3 URI>/<filename> | tar -xf - -C <base-path>
```
- rocksdb
```sh
s3get s3://euc1.parasnaps.io/kusama_rocksdb.tar | tar -xf - -C ~/.local/share/polkadot/chains/ksmcc3/
```
- paritydb
```sh
s3get s3://euc1.parasnaps.io/kusama_paritydb.tar | tar -xf - -C ~/.local/share/polkadot/chains/ksmcc3/
```

2. Run the polkadot node with:
- rocksdb
```sh
polkadot --chain=kusama --database=rocksdb --state-pruning=1000
```
- paritydb
```sh
polkadot --chain=kusama --database=paritydb --state-pruning=1000
```