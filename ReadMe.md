The BlockZone Wallet provides a walled designed to be used with split keys for SSH, GPG and X509.

The wallet is based on a hierarchical set of seeds, with a master seed on top.

Example
=======

24 words -> master seed.

master seed + SHA256("alica@atlanta.com") -> account seed.

account seed + SHA256("ssh:rsa:2048") -> protocol seed.

The protocol seed is used to generate the corresponding pub / private key.

As a default 100 pub / private keys are generated. One of those is registered as 
the active key in the blockchain.


API for Key Vault
=================

returns id of master-seed

void generateMasterSeed(int num_words)

int setMasterSeed(24 words)

return id of account-seed
 
int registerAccount("alica@atlanta.com", mid)

int registerProtocol("ssh:rsa:2048", aid)

pub_key getPubKey(pid)

more protocol specific signing services
