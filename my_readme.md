./geth --datadir node1 account new
INFO [02-10|17:17:05.518] Maximum peer count                       ETH=50 LES=0 total=50
Your new account is locked with a password. Please give a password. Do not forget this password.
Password:123
Repeat password:123

Your new key was generated

Public address of the key:   0x85a25F200cC71440587c1d0c915EBbAcd59C3Dc2
Path of the secret key file: node1\keystore\UTC--2021-02-10T22-17-11.143850100Z--85a25f200cc71440587c1d0c915ebbacd59c3dc2

- You can share your public address with anyone. Others need it to interact with you.
- You must NEVER share the secret key with anyone! The key controls access to your funds!
- You must BACKUP your key file! Without the key, it's impossible to access account funds!
- You must REMEMBER your password! Without the password, it's impossible to decrypt the key!
-----------------------------------------------------

 ./geth --datadir node2 account new
INFO [02-10|17:20:26.769] Maximum peer count                       ETH=50 LES=0 total=50
Your new account is locked with a password. Please give a password. Do not forget this password.
Password:
Repeat password:

Your new key was generated

Public address of the key:   0x9c729334188150a4fe9f9f9f60146dBA70FE4A92
Path of the secret key file: node2\keystore\UTC--2021-02-10T22-20-34.146694700Z--9c729334188150a4fe9f9f9f60146dba70fe4a92

- You can share your public address with anyone. Others need it to interact with you.
- You must NEVER share the secret key with anyone! The key controls access to your funds!
- You must BACKUP your key file! Without the key, it's impossible to access account funds!
- You must REMEMBER your password! Without the password, it's impossible to decrypt the key!

---------------------------







./puppeth
+-----------------------------------------------------------+
| Welcome to puppeth, your Ethereum private network manager |
|                                                           |
| This tool lets you create a new Ethereum network down to  |
| the genesis block, bootnodes, miners and ethstats servers |
| without the hassle that it would normally entail.         |
|                                                           |
| Puppeth uses SSH to dial in to remote servers, and builds |
| its network components out of Docker containers using the |
| docker-compose toolset.                                   |
+-----------------------------------------------------------+

Please specify a network name to administer (no spaces, hyphens or capital letters please)
> banana

Sweet, you can set this via --network=banana next time!

[32mINFO [0m[02-10|17:27:33.852] Administering Ethereum network           [32mname[0m=banana
[33mWARN [0m[02-10|17:27:33.861] No previous configurations found         [33mpath[0m=C:\\Users\\Minyeong\\.puppeth\\banana

What would you like to do? (default = stats)
 1. Show network stats
 2. Configure new genesis
 3. Track new remote server
 4. Deploy network components
> 2

What would you like to do? (default = create)
 1. Create new genesis from scratch
 2. Import already existing genesis
> 1

Which consensus engine to use? (default = clique)
 1. Ethash - proof-of-work
 2. Clique - proof-of-authority
> 2

How many seconds should blocks take? (default = 15)
> 15

Which accounts are allowed to seal? (mandatory at least one)
> 0x85a25F200cC71440587c1d0c915EBbAcd59C3Dc2
> 0x9c729334188150a4fe9f9f9f60146dBA70FE4A92
> 0x

Which accounts should be pre-funded? (advisable at least one)
> 0x85a25F200cC71440587c1d0c915EBbAcd59C3Dc2
> 0x9c729334188150a4fe9f9f9f60146dBA70FE4A92
> 0x

Should the precompile-addresses (0x1 .. 0xff) be pre-funded with 1 wei? (advisable yes)
> no

Specify your chain/network ID if you want an explicit one (default = random)
> 2525
[32mINFO [0m[02-10|17:30:30.966] Configured new genesis block

What would you like to do? (default = stats)
 1. Show network stats
 2. Manage existing genesis
 3. Track new remote server
 4. Deploy network components
> 2

Which folder to save the genesis specs into? (default = current)
  Will create banana.json, banana-aleth.json, banana-harmony.json, banana-parity.json
>
[32mINFO [0m[02-10|17:33:01.784] Saved native genesis chain spec          [32mpath[0m=banana.json
[31mERROR[0m[02-10|17:33:01.785] Failed to create Aleth chain spec        [31merr[0m="unsupported consensus engine"
[31mERROR[0m[02-10|17:33:01.785] Failed to create Parity chain spec       [31merr[0m="unsupported consensus engine"
[32mINFO [0m[02-10|17:33:01.791] Saved genesis chain spec                 [32mclient[0m=harmony [32mpath[0m=banana-harmony.json

What would you like to do? (default = stats)
 1. Show network stats
 2. Manage existing genesis
 3. Track new remote server
 4. Deploy network components
> [35mCRIT [0m[02-10|17:33:08.406] Failed to read user input                [35merr[0m=EOF
(base)

----------------------------------------------------------
./geth --datadir node1 init banana.json
INFO [02-10|17:39:49.799] Maximum peer count                       ETH=50 LES=0 total=50
INFO [02-10|17:39:50.235] Allocated cache and file handles         database=C:\\Users\\Minyeong\\Desktop\\homework18\\node1\\geth\\chaindata cache=16.00MiB handles=16
INFO [02-10|17:39:50.405] Writing custom genesis block
INFO [02-10|17:39:50.512] Persisted trie from memory database      nodes=3 size=457.00B time=6.9807ms gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B
INFO [02-10|17:39:50.731] Successfully wrote genesis state         database=chaindata hash=a14282…f8abe3
INFO [02-10|17:39:50.821] Allocated cache and file handles         database=C:\\Users\\Minyeong\\Desktop\\homework18\\node1\\geth\\lightchaindata cache=16.00MiB handles=16
INFO [02-10|17:39:50.995] Writing custom genesis block
INFO [02-10|17:39:51.022] Persisted trie from memory database      nodes=3 size=457.00B time=0s       gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B
INFO [02-10|17:39:51.178] Successfully wrote genesis state         database=lightchaindata hash=a14282…f8abe3
(base)
Minyeong@LAPTOP-E1HCTH1P MINGW64 ~/Desktop/homework18
$ ./geth --datadir node2 init banana.json
INFO [02-10|17:40:15.913] Maximum peer count                       ETH=50 LES=0 total=50
INFO [02-10|17:40:16.299] Allocated cache and file handles         database=C:\\Users\\Minyeong\\Desktop\\homework18\\node2\\geth\\chaindata cache=16.00MiB handles=16
INFO [02-10|17:40:16.373] Writing custom genesis block
INFO [02-10|17:40:16.381] Persisted trie from memory database      nodes=3 size=457.00B time=0s gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B
INFO [02-10|17:40:16.459] Successfully wrote genesis state         database=chaindata hash=a14282…f8abe3
INFO [02-10|17:40:16.478] Allocated cache and file handles         database=C:\\Users\\Minyeong\\Desktop\\homework18\\node2\\geth\\lightchaindata cache=16.00MiB handles=16
INFO [02-10|17:40:16.571] Writing custom genesis block
INFO [02-10|17:40:16.599] Persisted trie from memory database      nodes=3 size=457.00B time=996µs gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B
INFO [02-10|17:40:16.731] Successfully wrote genesis state         database=lightchaindata hash=a14282…f8abe3
(base)
Minyeong@LAPTOP-E1HCTH1P MINGW64 ~/Desktop/homework18
$

-----------------------------------------
./geth --datadir node1 --unlock 0x85a25F200cC71440587c1d0c915EBbAcd59C3Dc2 --mine --rpc --allow-insecure-unlock
----------------------------------------------------------
./geth --datadir node2 --unlock 0x9c729334188150a4fe9f9f9f60146dBA70FE4A92 --mine --port 30304 --bootnodes "enode://278004edeeddf6bdc559a6d9194cf45efae3862d4c79331f0f2b41272db26d84f9ff86c188e7f52e6f74db8a6b83ec8f7e31ae65664c2770ad7aec10766feba0@192.168.1.151:30303" --ipcdisable --allow-insecure-unlock

