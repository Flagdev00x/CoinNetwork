# Run a FLAG Validator
## Setting up a node
1. Git clone https://github.com/Flagdev00x/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/FLAG  /root/
```
3. Create an Account

```
cd /root/FLAG
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake FLAG coin, all you should do is sending your FLAG coin to the FLAG Consensus contract address over the FLAG network from the validator address.
    The FLAG Consensus contract address: 0xF631D903d6C31b606Ec527558e441108B6211af3
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to FLAG and send the FLAG coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /FLAG/nodes/validator/keys/FLAG/UTC--xxxx
    /FLAG/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
