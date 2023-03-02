# Run a BESC Validator
## Setting up a node
1. Git clone https://github.com/briannichols0702/BESCCoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r BESCCoinNetwork/node-example/BESC  /root/
```
3. Create an Account

```
cd /root/BESC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
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

    To stake BESC coin, all you should do is sending your BESC coin to the BESC Consensus contract address over the BESC network from the validator address.
    The BESC Consensus contract address: 0xc6119816bB72c980d99861FeF89F6ceDe5D362A5
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BESC and send the BESC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BESC/nodes/validator/keys/BESC/UTC--xxxx
    /BESC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
