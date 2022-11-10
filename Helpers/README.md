# Helper Resources
Here you can find some resources that can help you complete 4th challange

- Javascript library for Inery RPC API  
link : https://github.com/inery-blockchain/ineryjs

You can use whatever language you want to implement software solution 
The goal is to push transactions to inery blockchain via RPC API

## How to push transaction with RPC?

Pushing transaction can be executed by executing RPC post call
over inery node with endpoint https://NODE_IP/v1/chain/pushtransaction
and required post body parameters 
you can see documentation of api endpoint here : https://docs.inery.io/api/push-transaction

## Node
For NODE_IP you can replace with server ip or dns that host inery blockchain protocol.
Also Node should have specified options for API cors and port for https

### Use Existed Node RPC Endpoint
you can use "sys.blockchain-servers.world" as one of our nodes that have enabled API communication.

### Make your own Node RPC endpoint
you can make your node be able to respond to remote API calls by adding options in nodine runntime 

*nodine runntime represent proccess that was triggered with 
("./start.sh", "./hard_replay.sh" and "./genesis_start.sh") scripts

Edit "start.sh" script by adding following options after  `nodine \`

options required :
- allow headers

`--access-control-allow-headers=* \`

- add path to certificate

`--https-certificate-chain-file="PATH_TO_CERTIFICATE/cert.pem" \`

`--https-private-key-file="PATH_TO_CRETIFICATE/privkey.pem" \`

- add port for https

`--https-server-address 0.0.0.0:443 \`

PATH_TO_CERTIFICATE will be path to direcotry where you saved you api certificate.
If you dont have certificate you can add one by installing letsencypt certificate for ubuntu  20.04 
and you will find "cert.pem" and "privkey.pem" files once you sucesfully install certificate.

