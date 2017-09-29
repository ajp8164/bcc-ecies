Bcc ECIES
======

[![NPM Package](https://img.shields.io/npm/v/bcc-ecies.svg?style=flat-square)](https://www.npmjs.org/package/bcc-ecies)
[![Build Status](https://img.shields.io/travis/owstack/bcc-ecies.svg?branch=master&style=flat-square)](https://travis-ci.org/owstack/bcc-ecies)
[![Coverage Status](https://img.shields.io/coveralls/owstack/bcc-ecies.svg?style=flat-square)](https://coveralls.io/r/owstack/bcc-ecies)

A module for [bcc][bcc] that implements the [Elliptic Curve Integrated Encryption Scheme (ECIES)](http://en.wikipedia.org/wiki/Integrated_Encryption_Scheme). Uses ECIES symmetric key negotiation from public keys to encrypt arbitrarily long data streams.

See [the main bcc repo](https://github.com/owstack/bcc) or the [bcc guide on ECIES](http://bcc.io/guide/module/ecies/index.html) for more information.

Credit to [@ryanxcharles][ryan] for the original implementation.

## Attribution

This repository was created by copy forking [bitcore-ecies commit fa3e7f0](https://github.com/bitpay/bitcore-ecies/commit/fa3e7f0e0e47c9a6f5ec4e52e06ff8da45912b8c).

## Getting started

ECIES will allow to securely encrypt and decrypt messages using ECDSA key pairs (bitcoin cryptography).

```javascript
var alice = ECIES()
  .privateKey(aliceKey)
  .publicKey(bobKey.publicKey);

var message = 'some secret message';
var encrypted = alice.encrypt(message);

// encrypted will contain an encrypted buffer only Bob can decrypt

var bob = ECIES()
  .privateKey(bobKey)
  .publicKey(aliceKey.publicKey);
var decrypted = bob
  .decrypt(encrypted)
  .toString();
// decrypted will be 'some secret message'
```

## Contributing

See [CONTRIBUTING.md](https://github.com/owstack/bcc/blob/master/CONTRIBUTING.md) on the main bcc repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/owstack/bcc/blob/master/LICENSE).

Copyright 2017 Open Wallet Stack.
