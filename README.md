# 0x69420

Provide three arguments: a factory address (or contract that will call CREATE2), a caller address (for factory addresses that require it as a protection against frontrunning), and the keccak-256 hash of the initialization code of the contract that the factory will deploy. 



## install
### docker (nvidia/opencl)

- GPU: 1x RTX 3090
- Disk Space: 1.9 GB
- vast.ai

```bash
sudo apt install build-essential -y; \
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y; \
source "$HOME/.cargo/env"; \
git clone https://github.com/nuggxyz/0x69420 && cd 0x69420
```

###  m1 mac
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
brew update
brew install rustup && rustup-init
git clone https://github.com/nuggxyz/0x69420 && cd 0x69420
```

## run
```bash
echo "export INIT_CODE_HASH=$INIT_CODE_HASH"
echo "export CALLER=$ETH_FROM"
echo "export FACTORY=$FACTORY"

sed -i 's/0x4/0x40/g' src/lib.rs && cargo run --release "$FACTORY" "$ETH_FROM" "$INIT_CODE_HASH" 2
```
