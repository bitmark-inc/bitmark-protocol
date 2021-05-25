# Bitmarkd Improvement Plan

## 1. base on bitmarkd

**Security Issues**

-model security model checking

**Performance issue**

1. [Re/Continue] The time cost of synchronizing a node
    1. Network related
        1. Find the node
        2. Node synchronization
    2. Password related
        1. Encryption and decryption
        2. Checking and signing
    3. Time to sort out the database
    4. Network>>Password>>Database Stability
2. TX size problem
    1. UTXO pool will explode if it is too big
        -Cause calculation problems
        -Cause memory problems
        -Causes decentralization issues
    2. If it is too big, the blockchain will explode
    3. If it is too large, the transmission process will explode
    4. SQL will explode if it is too big
3. Tx robustness
    1. Add bitmarkd update proposal
        1. Limit bitmarkd transaction size
        2. Add other transaction types
            1. NFT redefines and in the future
            -Re-standardize the data type of NFT in detail

            -Can enter extension proposals
                1. Text
                2. Picture
                3. Videos
                4. 3d modeling
                5. Game authorization
                6. DRM
                7.. ..

    4. Current poor neck

    1. btc rhythm
    2. ltc rhythm
    3. base on layer 1
        1. Cross-chain difficulties, no public version
        2. Difficulty in layer 2 No public version
        3. Identity verification design No public version

## 2. base on other Chain

General solution

-Cross-chain mapping
    1. Let users choose whether to cross-chain
        1. A chain contract
        2. B chain contract
        3. relay server
            1. cross chain status
            2. Decentralized design
    2. Directly abolish bitmarkd and re-create all related transactions
-Brand issues

    Docktail brand: Lost all brand value in other chains

    Double-chain brand: a win-win situation (but bitmarkd, but the cross-chain mapping must be completed. Solution 1)

### new bitmarkd

### ethereum

### Bitcoin

### BSC

### Tron

### EOS