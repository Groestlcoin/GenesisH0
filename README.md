# GenesisH0
A python script for creating the parameters required for a unique genesis block. mainnet/testnet/regtest.

### Dependencies
    sudo pip install groestlcoin_hash construct==2.5.2

### Examples
Create the original genesis hash found in Groestlcoin

    python genesis.py -a mainnet -n 220035 -t 1395342829
Output:

    net: mainnet
    merkle hash: 3ce968df58f9c8a752306c4b7264afab93149dbc578bd08a42c446caaa6628bb
    pszTimestamp: Pressure must be put on Vladimir Putin over Crimea
    pubkey: 04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f
    time: 1395342829
    bits: 0x1e0fffff
    Searching for genesis hash..
    genesis hash found!
    nonce: 220035
    genesis hash: 00000ac5927c594d49cc0bdb81759d0da8297eb614683d3acb62f0703b639023

Create the testnet genesis hash found in Groestlcoin

    python genesis.py -a testnet -n 6556309 -t 1440000002
Output:

     net: testnet
     merkle hash: 3ce968df58f9c8a752306c4b7264afab93149dbc578bd08a42c446caaa6628bb
     pszTimestamp: Pressure must be put on Vladimir Putin over Crimea
     pubkey: 04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f
     time: 1440000002
     bits: 0x1e00ffff
     Searching for genesis hash..
     genesis hash found!
     nonce: 6556309
     genesis hash: 000000ffbb50fc9898cdd36ec163e6ba23230164c0052a28876255b7dcf2cd36

Create the testnet genesis hash found in Groestlcoin

    python genesis.py -a regtest -n 6556309 -t 1440000002
Output:

     net: regtest
     merkle hash: 3ce968df58f9c8a752306c4b7264afab93149dbc578bd08a42c446caaa6628bb
     pszTimestamp: Pressure must be put on Vladimir Putin over Crimea
     pubkey: 04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f
     time: 1440000002
     bits: 0x1e00ffff
     Searching for genesis hash..
     genesis hash found!
     nonce: 6556309
     genesis hash: 000000ffbb50fc9898cdd36ec163e6ba23230164c0052a28876255b7dcf2cd36

### Options
    Usage: genesis.py [options]

    Options:
      -h, --help show this help message and exit
      -t TIME, --time=TIME  the (unix) time when the genesisblock is created
      -z TIMESTAMP, --timestamp=TIMESTAMP
         the pszTimestamp found in the coinbase of the genesisblock
      -n NONCE, --nonce=NONCE
         the first value of the nonce that will be incremented
         when searching the genesis hash
      -a NET, --net=NET
         the network: [mainnet|testnet|regtest]
      -p PUBKEY, --pubkey=PUBKEY
         the pubkey found in the output script
      -v VALUE, --value=VALUE
         the value in coins for the output, full value (exp. in groestlcoin 0 - To get other value: Block Value * 100000000)
      -b BITS, --bits=BITS
         the target in compact representation, associated to a difficulty of 1
