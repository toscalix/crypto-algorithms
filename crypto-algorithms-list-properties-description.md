# SPDX Cryptographic Algorithms List properties description

## Id

* Description: unique identifier for every cryptographic algorithm. This list provides an identifier per algorithm.
* Values: string, where the usage of lower or upper case characters depend on each algorithm

## Name

* Description: widely accepted name provided by the author of the algorithm or a standardization body
* Values: string

## commonkeySize

* Description: the detected key size
* Values: <integer>, where <integer> is an integer, provided in bits. More than one value is possible, separated by the operator AND

## specifiedkeySize

* Description: the default key size or range determined by the authors of the algorithm, standardization or compliance bodies/agencies
* Values: one of these options, or a combination of them, are valid
   * <integer>, where <integer> is provided in bits. More than one value is possible, separated by the operator AND
   * <integer> TO <integer>, where <integer> are provided in bits, to express a range

## cryptoClass

* Description: cryptographic algorithms are categorized in classes. The classes are defined by the number of cryptographic keys that are used in conjunction with the algorithm.
   * Cryptographic hash functions do not require keys for their basic operation.
   * Symmetric-key algorithms transform data in a way that is fundamentally difficult to undo without knowledge of a secret key. The key is “symmetric” because the same key is used for a cryptographic operation and its inverse
   * Asymmetric-key algorithms, commonly known as public-key algorithms, use two related keys (i.e., a key pair) to perform their functions: a public key and a private key. The public key may be known by anyone; the private key should be under the sole control of the entity that “owns” the key pair. Even though the public and private keys of a key pair are related, knowledge of the public key cannot be used to determine the private key.
* Values: "Cryptographic-Hash-Function" , "Symetric-Key-Algorithm" or "Asymmetric-Key-Algorithm"

### cryptoSubClass

* Description: each class of algorithms is categorised in subclasses. These subclasses are based/inspired on:
   * NIST Special Publication (SP) [800-57](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf) Part 1, Rev. 4, January
   * Input from the SPDX Cryptographic Algorithms List Group members
* Values:
   * cryptoClass "Cryptographic-Hash-Function"
     * cryptoSubClass values: "Hash-Function" , "Password-Hashing" , "Message-Authentication-Code" , "Checksum"
  * cryptoClass "Symetric-Key-Algorithm"
     * cryptoSubClass values: "Block-Cipher" , "Stream-Cipher" , "Encoding" , "Random-Number-Generator" , "Key-Derivation"
  * cryptoClass "Asymmetric-Key-Algorithm"
     * cryptoSubClass values: "Public-Key-Encryption" , "Public-Key-Cipher" , "Elliptic-Curve-Cryptography" , "Digital-Signature" , "Post-Quantum-Cryptography" , "Protocol", "Hybrid-Cipher" or "Key-Exchange-Mechanism"

Notes: 
1. the subclasses has been added to the cryptoClass property, separated by a "/" character from the class. This specific way to structure the subclasses is WIP.
2. cryptoSubClass values are currently WIP
