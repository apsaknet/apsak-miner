# apsaK-miner
[![Build status](https://github.com/elichai/apsak-miner/workflows/ci/badge.svg)](https://github.com/elichai/apsak-miner/actions)
[![Latest version](https://img.shields.io/crates/v/apsak-miner.svg)](https://crates.io/crates/apsak-miner)
![License](https://img.shields.io/crates/l/apsak-miner.svg)
[![dependency status](https://deps.rs/repo/github/elichai/apsak-miner/status.svg)](https://deps.rs/repo/github/elichai/apsak-miner)

A Rust binary for file encryption to multiple participants. 


## Installation
### From Sources
With Rust's package manager cargo, you can install apsak-miner via:

```sh
cargo install apsak-miner
```

### From Binaries
The [release page](https://github.com/elichai/apsak-miner/releases) includes precompiled binaries for Linux, macOS and Windows.


# Usage
To start mining you need to run [apsakd](https://github.com/apsaknet/apsakd) and have an address to send the rewards to.
There's a guide here on how to run a full node and how to generate addresses: https://github.com/apsaknet/docs/blob/main/Getting%20Started/Full%20Node%20Installation.md

Help:
```
apsak-miner 0.2.1
A apsaK high performance CPU miner

USAGE:
    apsak-miner [FLAGS] [OPTIONS] --mining-address <mining-address>

FLAGS:
    -d, --debug                   Enable debug logging level
    -h, --help                    Prints help information
        --mine-when-not-synced    Mine even when apsakd says it is not synced, only useful when passing `--allow-submit-
                                  block-when-not-synced` to apsakd  [default: false]
        --testnet                 Use testnet instead of mainnet [default: false]
    -V, --version                 Prints version information

OPTIONS:
        --devfund <devfund-address>            Mine a percentage of the blocks to the apsaK devfund [default: Off]
        --devfund-percent <devfund-percent>    The percentage of blocks to send to the devfund [default: 1]
    -s, --apsakd-address <apsakd-address>      The IP of the apsakd instance [default: 127.0.0.1]
    -a, --mining-address <mining-address>      The apsaK address for the miner reward
    -t, --threads <num-threads>                Amount of miner threads to launch [default: number of logical cpus]
    -p, --port <port>                          apsaKd port [default: Mainnet = 17111, Testnet = 16211]
```

To start mining you just need to run the following:

`./apsak-miner --mining-address apsak:XXXXX`

This will run the miner on all the available CPU cores.

# Devfund
**NOTE: This feature is off by default** <br>
The devfund is a fund managed by the apsaK community in order to fund apsaK development <br>
A miner that wants to mine a percentage into the dev-fund can pass the following flags: <br>
`apsak-miner --mining-address= XXX --devfund=apsak:precqv0krj3r6uyyfa36ga7s0u9jct0v4wg8ctsfde2gkrsgwgw8jgxfzfc98` <br>
and can pass `--devfund-precent=XX.YY` to mine only XX.YY% of the blocks into the devfund (passing `--devfund` without specifying a percent will default to 1%)

# Donation Address
`apsak:qzvqtx5gkvl3tc54up6r8pk5mhuft9rtr0lvn624w9mtv4eqm9rvc9zfdmmpu`