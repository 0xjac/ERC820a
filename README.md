# ERC820a Pseudo-introspection Registry Contract
[![Build Status](https://img.shields.io/travis/jbaylina/ERC820a/master.svg?style=flat-square&maxAge=3600 )](https://travis-ci.org/jbaylina/ERC820a)
[![License](https://img.shields.io/npm/l/erc820a.svg?style=flat-square&maxAge=3600)](https://github.com/jbaylina/ERC820a/blob/master/LICENSE)
[![npm version](https://img.shields.io/npm/v/erc820a.svg?style=flat-square&maxAge=3600)](https://www.npmjs.com/package/erc820a)
[![npm downloads](https://img.shields.io/npm/dt/erc820a.svg?style=flat-square&maxAge=3600)](https://www.npmjs.com/package/erc820a)
[![Solidity version](https://img.shields.io/badge/Solidity-v0.5.3-ff69b4.svg?style=flat-square&maxAge=3600)](https://solidity.readthedocs.io/en/v0.5.3/installing-solidity.html)
[![EIP](https://img.shields.io/badge/EIP-820a-lightgrey.svg?style=flat-square&maxAge=3600)](https://eips.ethereum.org/EIPS/eip-820a)

*Universal registry smart contract where any address (contract or regular account) can register which interface it supports and which smart contract is responsible for its implementation.*

> :information_source: **[ERC820a] has superseded [ERC820].** :information_source:  
> [ERC820a] fixes the incompatibility in the [ERC165] logic which was introduced by the Solidty 0.5 update.  
> Have a look at the [official announcement][erc820a-annoucement], and the comments about the [bug][erc820-bug] and the [fix][erc820-fix].  
> Apart from this fix, [ERC820a] is functionally equivalent to [ERC820].
>
> :warning: [ERC820a] MUST be used in lieu of [ERC820]. :warning:

## Proposal
The official proposal can be found at: [eips.ethereum.org/EIPS/eip-820a][ERC820a].

## ERC820a Registry

This repository contains the official implementation of the [ERC820a registry] as defined in the [standard][ERC820a].

The address of the registry on **all chains** is:

<h4><pre>0x820a4875aA7900995D6f4ed84ab66651dd582aef</pre></h4>

## ERC820a Implementer

The [ERC820a implementer interface] is the interface any contract MUST implement if said contract implements an interface on behalf of another address via ERC820a.

## Compilation & Verification

> :warning: The `solc` compiler version `0.5.3+commit.10d17f24` must be present on the build machine. ([More info on installing solc][solc-install].)

The registry can be compiled from the source code using:

``` shell
npm run build
```

This will write the json artifacts for the registry in the `artifacts` folder and the standard output in the `build` folder.

### Verification

The address of the account creating the registry, the address of the registry and the raw signed transaction can be generated with:

``` shell
$ npm run info

> node js/info.js

RawTx:  0xf90a388085174876e800830c35008080b909e5608060405234801561001057600080fd5b506109c5806100206000396000f3fe608060405234801561001057600080fd5b50600436106100a5576000357c010000000000000000000000000000000000000000000000000000000090048063a41e7d5111610078578063a41e7d51146101d4578063aabbb8ca1461020a578063b705676514610236578063f712f3e814610280576100a5565b806329965a1d146100aa5780633d584063146100e25780635df8122f1461012457806365ba36c114610152575b600080fd5b6100e0600480360360608110156100c057600080fd5b50600160a060020a038135811691602081013591604090910135166102b6565b005b610108600480360360208110156100f857600080fd5b5035600160a060020a0316610570565b60408051600160a060020a039092168252519081900360200190f35b6100e06004803603604081101561013a57600080fd5b50600160a060020a03813581169160200135166105bc565b6101c26004803603602081101561016857600080fd5b81019060208101813564010000000081111561018357600080fd5b82018360208201111561019557600080fd5b803590602001918460018302840111640100000000831117156101b757600080fd5b5090925090506106b3565b60408051918252519081900360200190f35b6100e0600480360360408110156101ea57600080fd5b508035600160a060020a03169060200135600160e060020a0319166106ee565b6101086004803603604081101561022057600080fd5b50600160a060020a038135169060200135610778565b61026c6004803603604081101561024c57600080fd5b508035600160a060020a03169060200135600160e060020a0319166107ef565b604080519115158252519081900360200190f35b61026c6004803603604081101561029657600080fd5b508035600160a060020a03169060200135600160e060020a0319166108aa565b6000600160a060020a038416156102cd57836102cf565b335b9050336102db82610570565b600160a060020a031614610339576040805160e560020a62461bcd02815260206004820152600f60248201527f4e6f7420746865206d616e616765720000000000000000000000000000000000604482015290519081900360640190fd5b6103428361092a565b15610397576040805160e560020a62461bcd02815260206004820152601960248201527f4d757374206e6f74206265206120455243313635206861736800000000000000604482015290519081900360640190fd5b600160a060020a038216158015906103b85750600160a060020a0382163314155b156104ff5760405160200180807f455243383230415f4143434550545f4d4147494300000000000000000000000081525060140190506040516020818303038152906040528051906020012082600160a060020a031663249cb3fa85846040518363ffffffff167c01000000000000000000000000000000000000000000000000000000000281526004018083815260200182600160a060020a0316600160a060020a031681526020019250505060206040518083038186803b15801561047e57600080fd5b505afa158015610492573d6000803e3d6000fd5b505050506040513d60208110156104a857600080fd5b5051146104ff576040805160e560020a62461bcd02815260206004820181905260248201527f446f6573206e6f7420696d706c656d656e742074686520696e74657266616365604482015290519081900360640190fd5b600160a060020a03818116600081815260208181526040808320888452909152808220805473ffffffffffffffffffffffffffffffffffffffff19169487169485179055518692917f93baa6efbd2244243bfee6ce4cfdd1d04fc4c0e9a786abd3a41313bd352db15391a450505050565b600160a060020a03818116600090815260016020526040812054909116151561059a5750806105b7565b50600160a060020a03808216600090815260016020526040902054165b919050565b336105c683610570565b600160a060020a031614610624576040805160e560020a62461bcd02815260206004820152600f60248201527f4e6f7420746865206d616e616765720000000000000000000000000000000000604482015290519081900360640190fd5b81600160a060020a031681600160a060020a0316146106435780610646565b60005b600160a060020a03838116600081815260016020526040808220805473ffffffffffffffffffffffffffffffffffffffff19169585169590951790945592519184169290917f605c2dbf762e5f7d60a546d42e7205dcb1b011ebc62a61736a57c9089d3a43509190a35050565b600082826040516020018083838082843780830192505050925050506040516020818303038152906040528051906020012090505b92915050565b6106f882826107ef565b610703576000610705565b815b600160a060020a03928316600081815260208181526040808320600160e060020a031996909616808452958252808320805473ffffffffffffffffffffffffffffffffffffffff19169590971694909417909555908152600284528181209281529190925220805460ff19166001179055565b600080600160a060020a038416156107905783610792565b335b905061079d8361092a565b156107c357826107ad82826108aa565b6107b85760006107ba565b815b925050506106e8565b600160a060020a0390811660009081526020818152604080832086845290915290205416905092915050565b6000808061081d857f01ffc9a70000000000000000000000000000000000000000000000000000000061094c565b909250905081158061082d575080155b1561083d576000925050506106e8565b61084f85600160e060020a031961094c565b909250905081158061086057508015155b15610870576000925050506106e8565b61087a858561094c565b909250905060018214801561088f5750806001145b1561089f576001925050506106e8565b506000949350505050565b600160a060020a0382166000908152600260209081526040808320600160e060020a03198516845290915281205460ff1615156108f2576108eb83836107ef565b90506106e8565b50600160a060020a03808316600081815260208181526040808320600160e060020a0319871684529091529020549091161492915050565b7bffffffffffffffffffffffffffffffffffffffffffffffffffffffff161590565b6040517f01ffc9a7000000000000000000000000000000000000000000000000000000008082526004820183905260009182919060208160248189617530fa90519096909550935050505056fea165627a7a72305820f860e9f6b144d18d03165ad1b5f49ec11074b3e35b4aa84b7a57269f97f7538d00291ba08208208208208208208208208208208208208208208208208208208208208200a00820820820820820820820820820820820820820820820820820820820820820
Sender:  0x66bBAD577a9e2a9D7BD765562F9Ed657AD36C6d9
Contract: 0x820a4875aA7900995D6f4ed84ab66651dd582aef
```

Those values can be compared with the values in the [ERC820a standard][ERC820a].

### Metadata

The metadata---for the registry only---can be extrated using:

``` shell
node scripts/extract_metadata.js
```

This metadata can also be compared with the formated version in the [ERC820a standard][ERC820a].

### Vanity address

The vanity address of the registry---starting with `0x820a`---has been generated using the [`scripts/vanitygen.sh`] and [`scripts/vanitygen-info.js`] scripts.

## Authors
 - Jordi Baylina [@jbaylina][jbaylina]
 - Jacques Dafflon [@0xjac][0xjac]

## License

> The [ERC820a registry] is part of the  [ERC820a standard][ERC820a] and is therefore in the public domain via [CC0].

The authors waive all copyright and related or neighboring rights for the rest of this repository's content via [CC0]. A copy of the [CC0] waiver is included in the [LICENSE] file.


[ERC165]: https://eips.ethereum.org/EIPS/eip-165
[ERC820]: https://eips.ethereum.org/EIPS/eip-820
[ERC820a]: https://eips.ethereum.org/EIPS/eip-820a
[ERC820a registry]: https://github.com/jbaylina/ERC820a/blob/master/contracts/ERC820aRegistry.sol
[ERC820a implementer interface]: https://github.com/jbaylina/erc820a/blob/master/contracts/ERC820aImplementerInterface.sol
[`scripts/vanitygen.sh`]: https://github.com/jbaylina/erc820a/blob/master/scripts/vanitygen.sh
[`scripts/vanitygen-info.js`]: https://github.com/jbaylina/erc820a/blob/master/scripts/vanitygen-info.js
[jbaylina]: https://github.com/jbaylina
[0xjac]: https://github.com/0xjac
[CC0]: http://creativecommons.org/publicdomain/zero/1.0/
[LICENSE]: https://github.com/jbaylina/erc820a/blob/master/LICENSE
[solc-install]: https://solidity.readthedocs.io/en/v0.5.4/installing-solidity.html
[erc820a-annoucement]: https://github.com/ethereum/EIPs/issues/820#issuecomment-464109166
[erc820-bug]: https://github.com/ethereum/EIPs/issues/820#issuecomment-452465748
[erc820-fix]: https://github.com/ethereum/EIPs/issues/820#issuecomment-454021564

