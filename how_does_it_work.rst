.. _how_does_it_work:

#################
How does it work?
#################

LINK is an `Ethereum <https://ethereum.org/>`_ blockchain. A blockchain is a shared database that has a built-in cryptocurrency that is used to financially incentivize the neutrality of the database. No-one can be in charge of a blockchain.

The first blockchain was called Bitcoin. Pretty much the only thing in the Bitcoin database is how much Bitcoin each account has.

Ethereum takes this concept much further. Computer programs called `smart contracts <https://en.wikipedia.org/wiki/Smart_contract>`_ can be uploaded into the blockchain and these programs can then store data in the database that everyone has a copy of.

Many big projects are deployed on the Ethereum blockchain. But this presents a problem. One must assume that every software project has fatal bugs that will need to be fixed once they are discovered. Bitcoin had fatal problems early on that needed to be fixed and so did Ethereum.

Unfortunately, when the projects that are deployed on Ethereum need to be fixed they will have a very hard time because they will need to convince the entire blockchain to deploy their fix. This was the problem with The DAO crowdfunding project. An attacker stole $150m because of a bug in the smart contract. In attempting to fix this problem the Ethereum was split into two blockchains: Ethereum and Ethereum Classic.

The only purpose of the LINK blockchain is to run LINK. This means that whenever there is a problem that can only be fixed with a hard fork, it will not be difficult to convince the LINK community to adopt it.

The cryptocurrency of the LINK blockchain is also called LINK.

BlobStore
=========

The principle smart contract on the LINK blockchain is :ref:`blobstore`. It uses `IPFS <https://ipfs.io/>`_ as the underlying storage layer. Anyone can store a `blob <https://en.wikipedia.org/wiki/Binary_large_object>`_ of data and get back a :ref:`blobId`. This data is publically readable to everyone.

BlobStore has a rudimentary revisioning system so blobs can be updated while retaining their blobId and revision history.

Google Protocol Buffers
=======================

In order for the data stored in BlobStore to have meaning, there must be some sort of schema. `Google Protocol Buffers <https://developers.google.com/protocol-buffers/>`_ (Protobuf) is ideal for this. It has an upgradable schema system. This means that LINK has a system of content type inheritance. A standardized story type could be extended with new fields and still be readable by software that only knows how to read standard stories.

Anyone can make a new type. Example types are user profiles, media metadata, tweets, reddit posts, blog posts, business information, reviews, etc.

Protobuf encodes the data very tightly. This data is then compressed with `Google Brotli <https://en.wikipedia.org/wiki/Brotli>`_. This minimizes the cost of storing information on LINK.

Additional smart contracts
==========================

Anyone can deploy additional smart contracts onto the LINK blockchain. An important example would be a feed contract that would provide functionality akin to RSS / Twitter / YouTube.

Other examples would be contracts to vote for content or tag content.
