
Se vuoi mandare a diversi address è da modificare nel constructor

in _tokenTransfer si può implementare una logica diversa per per esempio burnare i token (0x o 0000)
oppure mandarli a te stesso

https://github.com/jklepatch/eattheblocks/tree/master/live-trainings/1-fork-safemoon
truffle config 
riga 79 ci sono le config delle BSC
gas serve a un cazzo
gas price boh
lui usa HDWallet perchè ha un wallet hardware.. bisogna cambiare la libreria a seconda del wallet che si usa

#PancakeSwap on BSC testnet:

Factory: 0x6725F303b657a9451d8BA641348b6761A6CC7a17

Router: 0xD99D1c33F9fC3444f8101754aBC46c52416550D1

PancakeSwap V2 router
0x10ED43C718714eb63d5aA57B78B54704E256024E

truffle compile
Bisogna avere dei wbnb della testnet per deployarci probabilmente (per pagare le fee)
ricevere bnb sulla testnet -> truffle develop -> prendi l'address e cerchi su google la testnet bsc -> ti fai mettere bnb su quello
poi cambi l'address nel fork di safemoon
truffle migrate --reset --network bscTestnet
truffle migrate --reset --network bsc
truffle config -> plugins truffle-plugin-verify api keys di bsc scan
devDependencies
truffle verify ma che cazzo ne so
la mnemonic (il mio address) va settato nella truffle config

su bsc scan si può poi verificare il contract

aggiungere updateDex per fare l'update del pancakeswap address nel constructor

how to do the token distribution

do an initial dex offering
create a liquidity pool and provide liquidity yourself
prendi il 10% e lo pairi con un tot di WBNB

do an airdrop e gliene mandi per free

non c'è burn nel contratto di safemoon, li hanno bruciati alla cazzo di cane a mano
c'è un esempio di burn automatico in Token.sol del suo repo schifoso

sul suo channel c'è l'esempio (2/3 settimane fa) su come si fa airdrop

Maybe can you give your opinion of this point : The identified vulnerabilities allow any perpetrator to set commissions for $SAFEMOON tokens as high as 100%, conduct malignant rug-pulling practices, exclude token holders from commission distributions, temporarily block token transfer, or render smart contracts permanently inoperable. Moreover, at least four of the vulnerabilities can be launched in combination, thus multiplying the inflicted damage in favor of the malevolent actors.

Per spostare la liquidity da una versione di pancake all'altra oltre a fare l'update bisogna fare redeem della pool e poi metterla su quello nuovo

lock liquidity on DxSale


cos'è la reflection?