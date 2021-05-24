# bitmarkd uml


```
sudo apt-get update
sudo apt install libargon2-0-dev uuid-dev libzmq3-dev git
```

go 語言環境

```jsx
sudo apt  install golang-go

nano ${HOME}/.bashrc
export GOROOT=/usr/lib/go
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

下載bitmarkd

```jsx
git clone https://github.com/bitmark-inc/bitmarkd
cd bitmarkd
go install -v ./...
```

修正 主網、比特幣、萊特幣、網路IP

```jsx
mkdir -p ${HOME}/.config/bitmarkd
cp ${HOME}/bitmarkd/command/bitmarkd/bitmarkd.conf.sample  ~/.config/bitmarkd/bitmarkd.conf
${EDITOR} ${HOME}/.config/bitmarkd/bitmarkd.conf
```

```jsx
-- [1] select the chain of the network for peer connections
--     cross chain networking connects will not work
-- Uncomment One:
chain = "bitmark"
--chain = "testing"
--chain = "local"   -- for regression testing only
--chain = "testing"
-- [2] setup coin addresses for recorder payments
--     the chain selection above will determine which
--     address to use
bitcoin_address = {
--    test = "***REPLACE-WITH-REAL-TEST-BTC-ADDRESS***",
    live = "1Mw7K3oHiG93F9hsamHu922Dr9Z1WKygRc",
}
litecoin_address = {
--    test = "***REPLACE-WITH-REAL-TEST-LTC-ADDRESS***",
    live = "Lev9zAUbbRNc1dtGxEKBMSL1j4mAp41FSL",
}
-- [3] public IPs of firewall or external interface
--     Either or both IPv4 and IPv6 can be added depending
--     on the network settings
announce_ips = {
    "34.71.197.134",
    --"a.b.c.d",  -- IPv4
    --"x::y:z",   -- IPv6
}
```

初始化鑰匙

```jsx
bitmarkd --config-file="${HOME}/.config/bitmarkd/bitmarkd.conf" gen-peer-identity "${HOME}/.config/bitmarkd/"
bitmarkd --config-file="${HOME}/.config/bitmarkd/bitmarkd.conf" gen-rpc-cert "${HOME}/.config/bitmarkd/"
bitmarkd --config-file="${HOME}/.config/bitmarkd/bitmarkd.conf" gen-proof-identity "${HOME}/.config/bitmarkd/"
```

補上 bitmarkd.conf.sub

```jsx
cd ${HOME}/.config/bitmarkd/
wget https://raw.githubusercontent.com/bitmark-inc/bitmarkd/master/command/bitmarkd/bitmarkd.conf.sub
```

修正 nano ${HOME}/.config/bitmarkd/bitmarkd.conf.sub

```jsx
-- set the directory for data and log files
--M.data_directory = arg[0]:match("^(.*/)")  -- dir from configuration file
M.data_directory = "."                     -- current directory
--M.data_directory = "/var/lib/bitmarkd"    -- absolute path
```

```jsx
bitmarkd --config-file="${HOME}/.config/bitmarkd/bitmarkd.conf" start
```

 觀測

```jsx
tail -f ${HOME}/.config/bitmarkd/log/bitmarkd.log
```

# UML

account

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/account.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/account.svg)

announce
asset

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/asset.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/asset.svg)

avl

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/avl.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/avl.svg)

background

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/background.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/background.svg)

block

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/block.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/block.svg)

blockdigest

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/blockdigest.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/blockdigest.svg)

blockheader

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/blockheader.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/blockheader.svg)

blockrecord

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/blockrecord.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/blockrecord.svg)

chain

command
configuration
constants
counter
currency
debian
difficulty
doc
fault
genesis
hooks
merkle
messagebus
mode
ownership
pay
payment
peer
proof

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/proof.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/proof.svg)

publish
reservoir
rpc
scripts
storage
testing
transactionrecord

![bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/transactionrecord.svg](bitmarkd%20uml%20233dfdb3eca642b1a8683bae79439bb5/transactionrecord.svg)

util
vendor
zmqutil