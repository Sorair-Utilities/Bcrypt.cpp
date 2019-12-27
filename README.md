# Bcrypt.cpp
A C++ wrapper around [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) (origin: Open BSD) password hashing

## How to use

Here an example how to use this wrapper class

```cpp
#include "bcrypt.h"
#include <iostream>
#include <string>


int main()
{

    std::string password = "top_secret";

    std::string hash = bcrypt::generateHash(password);

    std::cout << "Hash: " << hash << std::endl;

    std::cout << "\"" << password << "\" : " << bcrypt::validatePassword(password,hash) << std::endl;
    std::cout << "\"wrong\" : " << bcrypt::validatePassword("wrong",hash) << std::endl;

    return 0;
}

```

output:

```
Hash: $2b$10$9ngimRxnytdaWoCd4NKPneEb/9dW24/B830XpS8TbExVeGKbukYbG
"top_secret" : 1
"wrong" : 0
```

[check online https://bcrypt-generator.com](https://bcrypt-generator.com/)

