Type Registry
=============

`Source <https://github.com/link-blockchain/link-type-registry/blob/ae129b1b7d1f60514cba87be548ed2b18d04980f/src/link_type_registry.sol>`_

Deployment address: ``0xb41a413db14f8bbd82e23393688f169e527e88f0``

Solidity 0.4.11 with optimizations.

 
Every item of content stored on Link has a content type. Examples of potential content types are tweets, comments, blog posts, media metadata and user profiles.

Link has a hierarchical system of content types. Except for the root content type, every content type has a parent content type that it extends. The schema for the root content type is empty.

https://github.com/link-blockchain/link-type-registry/blob/1.0.0/src/link_type_registry.sol#L60

Each content type is identified by an integer, the typeId. The typeId for each content type is issued by the Type Registry smart contract. When creating a new content type, the `addContentType() <https://github.com/link-blockchain/link-type-registry/blob/1.0.0/src/link_type_registry.sol#L60>`_ method must be called. ``parent`` must be the typeId of the content type that the new one is extending. ``uri`` should be a link to an immuntable commit in a repo that is forked or branched from the URI of the parent content type.
