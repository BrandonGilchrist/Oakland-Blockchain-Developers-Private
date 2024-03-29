# geth and IPFS Cheatsheet
## The go-ethereum command line interface

## USAGE:
   geth [options] command [command options] [arguments...]
   
## VERSION:
   1.6.7-stable-ab5646c5
   
## COMMANDS:
Command | Description 
--- | --- |
   init        | Bootstrap and initialize a new genesis block
   import      | Import a blockchain file
   export      | Export blockchain into file
   removedb    | Remove blockchain and state databases
   dump        | Dump a specific block from storage
   monitor     | Monitor and visualize node metrics
   account     | Manage accounts
   wallet      | Manage Ethereum presale wallets
   console     | Start an interactive JavaScript environment
   attach      | Start an interactive JavaScript environment (connect to node)| 
   js          | Execute the specified JavaScript files
   makedag     | Generate ethash DAG (for testing)
   version     | Print version numbers
   bug         | opens a window to report a bug on the geth repo
   license     | Display license information
   dumpconfig  | Show configuration values
   help, h     | Shows a list of commands or help for one command
   
## ETHEREUM OPTIONS:
Command | Description 
--- | --- |
  --config value                           |TOML configuration file
  --datadir "/Users/bxb/Library/Ethereum"  |Data directory for the databases and keystore
  --keystore                               |Directory for the keystore (default = inside the datadir)
  --nousb                                  |Disables monitoring for and managine USB hardware wallets
  --networkid value                        |Network identifier (integer, 1=Frontier, 2=Morden (disused), 3=Ropsten, 4=Rinkeby) (default: 1)
  --testnet                                |Ropsten network: pre-configured proof-of-work test network
  --rinkeby                                |Rinkeby network: pre-configured proof-of-authority test network
  --dev                                    |Developer mode: pre-configured private network with several debugging flags
  --syncmode "fast"                        |Blockchain sync mode ("fast", "full", or "light")
  --ethstats value                         |Reporting URL of a ethstats service (nodename:secret@host:port)
  --identity value                         |Custom node name
  --lightserv value                        |Maximum percentage of time allowed for serving LES requests (0-90) (default: 0)
  --lightpeers value                       |Maximum number of LES client peers (default: 20)
  --lightkdf                               |Reduce key-derivation RAM & CPU usage at some expense of KDF strength
  
## ETHASH OPTIONS:
Command | Description 
--- | --- |
  --ethash.cachedir                     |Directory to store the ethash verification caches (default = inside the datadir)
  --ethash.cachesinmem value            |Number of recent ethash caches to keep in memory (16MB each) (default: 2)
  --ethash.cachesondisk value           |Number of recent ethash caches to keep on disk (16MB each) (default: 3)
  --ethash.dagdir "/Users/bxb/.ethash"  |Directory to store the ethash mining DAGs (default = inside home folder)
  --ethash.dagsinmem value              |Number of recent ethash mining DAGs to keep in memory (1+GB each) (default: 1)
  --ethash.dagsondisk value             |Number of recent ethash mining DAGs to keep on disk (1+GB each) (default: 2)
  
## TRANSACTION POOL OPTIONS:
Command | Description 
--- | --- |
  --txpool.nolocals            |Disables price exemptions for locally submitted transactions
  --txpool.pricelimit value    |Minimum gas price limit to enforce for acceptance into the pool (default: 1)
  --txpool.pricebump value     |Price bump percentage to replace an already existing transaction (default: 10)
  --txpool.accountslots value  |Minimum number of executable transaction slots guaranteed per account (default: 16)
  --txpool.globalslots value   |Maximum number of executable transaction slots for all accounts (default: 4096)
  --txpool.accountqueue value  |Maximum number of non-executable transaction slots permitted per account (default: 64)
  --txpool.globalqueue value   |Maximum number of non-executable transaction slots for all accounts (default: 1024)
  --txpool.lifetime value      |Maximum amount of time non-executable transaction are queued (default: 3h0m0s)
  
## PERFORMANCE TUNING OPTIONS:
Command | Description 
--- | --- |
  --cache value            |Megabytes of memory allocated to internal caching (min 16MB / database forced) (default: 128)
  --trie-cache-gens value  |Number of trie node generations to keep in memory (default: 120)
  
## ACCOUNT OPTIONS:
Command | Description 
--- | --- |
  --unlock value    |Comma separated list of accounts to unlock
  --password value  |Password file to use for non-inteactive password input
  
## API AND CONSOLE OPTIONS:
Command | Description 
--- | --- |
  --rpc                  |Enable the HTTP-RPC server
  --rpcaddr value        |HTTP-RPC server listening interface (default: "localhost")
  --rpcport value        |HTTP-RPC server listening port (default: 8545)
  --rpcapi value         |API's offered over the HTTP-RPC interface
  --ws                   |Enable the WS-RPC server
  --wsaddr value         |WS-RPC server listening interface (default: "localhost")
  --wsport value         |WS-RPC server listening port (default: 8546)
  --wsapi value          |API's offered over the WS-RPC interface
  --wsorigins value      |Origins from which to accept websockets requests
  --ipcdisable           |Disable the IPC-RPC server
  --ipcpath              |Filename for IPC socket/pipe within the datadir (explicit paths escape it)
  --rpccorsdomain value  |Comma separated list of domains from which to accept cross origin requests (browser enforced)
  --jspath loadScript    |JavaScript root path for loadScript (default: ".")
  --exec value           |Execute JavaScript statement
  --preload value        |Comma separated list of JavaScript files to preload into the console
  
## NETWORKING OPTIONS:
Command | Description 
--- | --- |
  --bootnodes value     |Comma separated enode URLs for P2P discovery bootstrap (set v4+v5 instead for light servers)
  --bootnodesv4 value   |Comma separated enode URLs for P2P v4 discovery bootstrap (light server, full nodes)
  --bootnodesv5 value   |Comma separated enode URLs for P2P v5 discovery bootstrap (light server, light nodes)
  --port value          |Network listening port (default: 30303)
  --maxpeers value      |Maximum number of network peers (network disabled if set to 0) (default: 25)
  --maxpendpeers value  |Maximum number of pending connection attempts (defaults used if set to 0) (default: 0)
  --nat value           |NAT port mapping mechanism (any|none|upnp|pmp|extip:<IP>) (default: "any")
  --nodiscover          |Disables the peer discovery mechanism (manual peer addition)
  --v5disc              |Enables the experimental RLPx V5 (Topic Discovery) mechanism
  --netrestrict value   |Restricts network communication to the given IP networks (CIDR masks)
  --nodekey value       |P2P node key file
  --nodekeyhex value    |P2P node key as hex (for testing)
  
## MINER OPTIONS:
Command | Description 
--- | --- |
  --mine                    |Enable mining
  --minerthreads value      |Number of CPU threads to use for mining (default: 8)
  --etherbase value         |Public address for block mining rewards (default = first account created) (default: "0")
  --targetgaslimit value    |Target gas limit sets the artificial target gas floor for the blocks to mine (default: 4712388)
  --gasprice "18000000000"  |Minimal gas price to accept for mining a transactions
  --extradata value         |Block extra data set by the miner (default = client version)
  
## GAS PRICE ORACLE OPTIONS:
Command | Description 
--- | --- |
  --gpoblocks value      |Number of recent blocks to check for gas prices (default: 10)
  --gpopercentile value  |Suggested gas price is the given percentile of a set of recent transaction gas prices (default: 50)
  
## VIRTUAL MACHINE OPTIONS:
Command | Description 
--- | --- |
  --vmdebug  |Record information useful for VM and contract debugging
  
## LOGGING AND DEBUGGING OPTIONS:
Command | Description 
--- | --- |
  --metrics                 |Enable metrics collection and reporting
  --fakepow                 |Disables proof-of-work verification
  --nocompaction            |Disables db compaction after import
  --verbosity value         |Logging verbosity: 0=silent, 1=error, 2=warn, 3=info, 4=debug, 5=detail (default: 3)
  --vmodule value           |Per-module verbosity: comma-separated list of <pattern>=<level> (e.g. eth/*=5,p2p=4)
  --backtrace value         |Request a stack trace at a specific logging statement (e.g. "block.go:271")
  --debug                   |Prepends log messages with call-site location (file and line number)
  --pprof                   |Enable the pprof HTTP server
  --pprofaddr value         |pprof HTTP server listening interface (default: "127.0.0.1")
  --pprofport value         |pprof HTTP server listening port (default: 6060)
  --memprofilerate value    |Turn on memory profiling with the given rate (default: 524288)
  --blockprofilerate value  |Turn on block profiling with the given rate (default: 0)
  --cpuprofile value        |Write CPU profile to the given file
  --trace value             |Write execution trace to the given file
  
## WHISPER (EXPERIMENTAL) OPTIONS:
Command | Description 
--- | --- |
  --shh                       |Enable Whisper
  --shh.maxmessagesize value  |Max message size accepted (default: 1048576)
  --shh.pow value             |Minimum POW accepted (default: 0.2)

## DEPRECATED OPTIONS:
Command | Description 
--- | --- |
  --fast   |Enable fast syncing through state downloads
  --light  |Enable light client mode
  
## MISC OPTIONS:
Command | Description 
--- | --- |
  --help, -h  |show help
  

# IPFS
USAGE
  ipfs - Global p2p merkle-dag filesystem.

  ipfs [--config=<config> | -c] [--debug=<debug> | -D] [--help=<help>] [-h=<h>] [--local=<local> | -L] [--api=<api>] <command> 
  
## BASIC COMMANDS:
Command | Description 
--- | --- |
    init          |Initialize ipfs local configuration
    add <path>    |Add a file to IPFS
    cat <ref>     |Show IPFS object data
    get <ref>     |Download IPFS objects
    ls <ref>      |List links from an object
    refs <ref>    |List hashes of links from an object
  
## DATA STRUCTURE COMMANDS
Command | Description 
--- | --- |
    block         |Interact with raw blocks in the datastore
    object        |Interact with raw dag nodes
    files         |Interact with objects as if they were a unix filesystem
    dag           |Interact with IPLD documents (experimental)
  
## ADVANCED COMMANDS
Command | Description 
--- | --- |
    daemon        |Start a long-running daemon process
    mount         |Mount an IPFS read-only mountpoint
    resolve       |Resolve any type of name
    name          |Publish and resolve IPNS names
    key           |Create and list IPNS name keypairs
    dns           |Resolve DNS links
    pin           |Pin objects to local storage
    repo          |Manipulate the IPFS repository
    stats         |Various operational stats
    p2p           |Libp2p stream mounting
    filestore     |Manage the filestore (experimental)
  
## NETWORK COMMANDS
Command | Description 
--- | --- |
    id            |Show info about IPFS peers
    bootstrap     |Add or remove bootstrap peers
    swarm         |Manage connections to the p2p network
    dht           |Query the DHT for values or peers
    ping          |Measure the latency of a connection
    diag          |Print diagnostics
  
## TOOL COMMANDS
 Command | Description 
--- | --- |
    config       | Manage configuration
    version      | Show ipfs version information
    update       | Download and apply go-ipfs updates
    commands     | List all available commands
  
  Use 'ipfs <command> --help' to learn more about each command.
  
  ipfs uses a repository in the local file system. By default, the repo is located
  at ~/.ipfs. To change the repo location, set the $IPFS_PATH environment variable:
  
    export IPFS_PATH=/path/to/ipfsrepo
  
  EXIT STATUS
  
  The CLI will exit with one of the following values:
  
  0     Successful execution.
  1     Failed executions.
   
