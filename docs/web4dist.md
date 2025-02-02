# Web4 Distribution


using https://github.com/vgrichina/web4-min-contract

first deploy web4-min-contract
```sh
near deploy web4.sleet.testnet web4-min.wasm
near deploy web4.sleet.near web4-min.wasm
```

near cli network
```sh
export NEAR_NETWORK=testnet
export NEAR_NETWORK=mainnet
echo $NEAR_NETWORK 
echo $NEAR_ENV
```

deploy

```sh
npx web4-deploy SLEET_WEB web4.sleet.testnet --nearfs
npx web4-deploy SLEET_WEB web4.sleet.near --nearfs
```
- can be run with or without --nearfs

get ipf url from last command
```sh
near call <contract_id> <method_name> '{"url":"ipfs://bafybeidr3fmocmsvy4wkj2lpjuycbblxrqtipo3j76son5b6fxfhn4mwim"}'

near call web4.sleet.testnet web4_setStaticUrl  '{"url":"ipfs://bafybeidr3fmocmsvy4wkj2lpjuycbblxrqtipo3j76son5b6fxfhn4mwim"}' --use-account  web4.sleet.testnet

near call web4.sleet.near web4_setStaticUrl  '{"url":"ipfs://bafybeidr3fmocmsvy4wkj2lpjuycbblxrqtipo3j76son5b6fxfhn4mwim"}' --use-account web4.sleet.near
```


also locally with ipfs
```sh
ipfs add -r web_playground
```


---




near subaccunt setup

```sh
near create-account web4.sleet.testnet --masterAccount sleet.testnet --initialBalance 1
near create-account web4.sleet.near --masterAccount sleet.near --initialBalance 0.5
```

remember to export account
```sh
# export
near account export-account web4.sleet.testnet
near account export-account web4.sleet.near

#view
near view-account 
```