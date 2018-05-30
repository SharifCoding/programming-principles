![bcrypt](https://i.stack.imgur.com/m8opZ.png)

## Bcrypt Encryption
___bcrypt is an adaptive function: over time, the iteration count can be increased to make it slower, so it remains resistant to brute-force search attacks even with increasing computation power.___

#### Introduction
Almost any application will eventually need to store a collection of passwords or another type of data that has to be stored using a hashing algorithm. Blogs, forums, issue trackers, they all need to store user data and these passwords. Hashing is the greatest way for protecting passwords and considered to be pretty safe for ensuring the integrity of data or password.

There are some weaknesses in cryptographic hash algorithm that allows an attacker to calculate the original value of a hashed password:

<b>Brute Force attack:</b> Hashes can’t be reversed, so instead of reversing the hash of the password, an attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value. Using a modern computer one can crack a 16 Character Strong password in less than an hour, thanks to GPU.

<b>Hash Collision attack:</b> Hash functions have infinite input length and a predefined output length, so there is inevitably going to be the possibility of two different inputs that produce the same output hash. MD5, SHA1, SHA2 are vulnerable to Hash Collision Attack i.e. two input strings of a hash function that produce the same hash result.

To overcome such issues, we need algorithms which can make the brute force attacks slower and minimize the impact. BCrypt algorithms use a technique called Key Stretching.

#### BCrypt
```php
// Generate a password using a random salt 
password_hash($password, PASSWORD_BCRYPT);
// Generate a password with a known salt
password_hash($password, PASSWORD_BCRYPT, array("salt" => $salt));
// This will cause crypt to generate a bcrypt hash
$salt = '$2y$10$' . mcrypt_create_iv(22);
$salted_password = crypt($password, $salt)
```
BCrypt is based on the Blowfish block cipher cryptomatic algorithm and takes the form of an adaptive hash function.

Using a Key Factor, BCrypt is able to adjust the cost of hashing. With Key Factor changes, the hash output can be influenced. In this way, BCrypt remains extremely resistant to hacks, especially a type of password cracking called rainbow table.

This Key Factor will continue to be a key feature as computers become more powerful in the future. Well, because it compensates for these powerful computers and slows down hashing speed significantly. Ultimately slowing down the cracking process until it’s no longer a viable strategy.

[Bcrypt](https://en.wikipedia.org/wiki/Bcrypt)
[Use BCrypt Fool!](https://yorickpeterse.com/articles/use-bcrypt-fool/)

#### [Return: Express README](../README.md)
