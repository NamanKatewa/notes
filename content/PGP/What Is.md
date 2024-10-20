# **Pretty Good Privacy**

-  A method to Decrypt & Encrypt email or data for communication.
- Considered one of the most secure ways to communicate

# Brief Overview of its working

- Combination of cryptography, data compression & hashing.
## **Three Step Process**

- **Generates a session key :** PGP first creates a temporary, unique key (called a session key) to encrypt the actual message. This key is only used once & is extremely hard to guess.

- **Encrypt the session key :** The session key is then locked (encrypted) using the recipient's public key. The public key is something the recipient can share with anyone, so other can send them secure messages.

- **Decrypt the Session Key :** When the recipient gets the encrypted message, they use their private key to unlock the session key. Once the session key is unlocked, they can decrypt the actual message.