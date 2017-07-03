.. _blobstore:

BlobStore
=========

BlobStore is the principle smart contract system for Link. All base content is registered with BlobStore. `IPFS <https://ipfs.io/>`_ is used as the storage layer.

Useful links
------------

* `Source code <https://github.com/link-blockchain/blobstore>`_

* `Issue tracker <https://github.com/link-blockchain/blobstore/issues>`_

* `Solidity API <http://solidity-apis.link-blockchain.org/docs/BlobStore/>`_

Properties
----------

BlobStore has the following properties:

* Timestamped
   The approximate time that every blob is published is recorded on the blockchain.

* World-readable
   Every blob published can be read by anyone. The only way to avoid this would be to encrypt the blob before publishing it.

* Immutable
    While a blob can be "retracted", it can never really be deleted because the transaction that created it will be archived for eternity on full nodes.
    
* Revisioned
   BlobStore has a rudimentary revisioning system built-in where a blob can have multiple revisions, e.g. for editing posts. More sophisticated revisioning systems can be built on top of BlobStore where each blob is a revision.

* Ownership
   Each blob can have an owner. Only the owner can modify a blob, change blob settings, or transfer ownership to another address.
   
* Configurable
   Each blob has the following flags that can be set:

   * Updatable
      The contents of the blob can be changed. Once disabled this flag cannot be re-enabled.
   * Enfore Revisions
      When updating the blob a new revision must be created. It is not possible to retract revisions. Once enabled, this flag cannot be disabled.
   * Retractable
      The blob in its entirety can be retracted. This is unaffected by Enforce Revisions. The blobId of a retracted blob can never be used again. Once disabled this flag cannot be re-enabled.
   * Transferable
      The blob can be transfered to another user (if they accept it), or disowned completely. Once disabled this flag cannot be re-enabled. At creation time blobs can also be flagged as anonymous to not have an owner associated. An alternative to transferable blobs is to use a proxy account with transferable ownership as the blob owner.

* Scalable
   Only a bare-minimum of information is stored in contract state. IPFS is used for actual content storage.
   
* Upgradability
    BlobStore is an upgradable system. Due to a security vulnerability, new storage system, or gas cost improvements a new BlobStore contract may be deployed.

* Unit tests
   BlobStore has tests written in Solidity using the `Dapp <https://dapp.readthedocs.io/>`_ framework.

.. _blobid:


blobId
------

Each blob has a 20 byte blobId that is unique to the contract that generated it. The blobId can be further classified to indicate which contract and blockchain the blob is on.

* Off-chain
   There is considered to be an ordered list of BlobStore contracts. For example, the first contract would be #0. The next one would be #1. 20 byte blobIds can be prefixed to indicate which contract the blob is in, or this can be assumed from context.

   Client software should have a hard coded whitelist of BlobStore contracts that its knows how to read from.

* On-chain
   New BlobStore contracts register with the BlobStore registration contract. When a blobId is stored in a smart contract, it must be stored with the 12 byte BlobStore contractId. This way the smart contract can look up the address of any BlobStore contract in the registration contract. This is essential to future-proof smart contracts that need to communicate with BlobStore contracts.

Deployments
-----------

All current deployments of BlobStore contracts on Link were compiled with Solidity 0.4.11 with optimizations enabled.

``Git hash: `073805c693d008b3cb258d50aa79473103680580 <https://github.com/link-blockchain/blobstore/tree/073805c693d008b3cb258d50aa79473103680580/src>`_ 12``


BlobStoreRegistry contract address: ``0x767f8a42f169038d18416b66f7241bf70fffc329``

BlobStore #0
````````````
IPFS with SHA256 hash.

contract address: ``0x73d1bdf1550cb6506b5728c9f11cd1acacfb2095``

BlobStore contractId: ``0x28ccad938027378a568fb84f``
