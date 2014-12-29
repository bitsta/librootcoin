# librootcoin v0.1 - EXPERIMENTAL SOFTWARE! 

## Introduction

*librootcoin* is an open-source jsron-rpc wrapper for interaction with a
rootcoin-deamon or wallet. 

##Dependencies

Librootcoin depends on openssl, cmake, curl, libjson-cpp, libjson-rpc-cpp, librootcoin and boost
to be built.

```sh
sudo apt-get install cmake libcurl4-openssl-dev libjsoncpp-dev
```

**Build and install librootcoin**

```sh
git clone https://github.com/bitsta/librootcoin
mkdir librootcoin/build
cd build
cmake .. && make
sudo make install
```

###Usage

librootcoin can be used with ANY cryptocurrency. 

rootkey.cpp
```
#include <librootcoin.h>

using namespace std;

int main()
{
    std::string user = "username";		//RootCoin.conf
    std::string pw = "password";		//RootCoin.conf
    std::string host = "127.0.0.1";		//daemon-host
    int port = 27377;					// rpc-port
    std::string key = "";
    std::string public = "RSCWE42cc2WS25jAjFczMvZym63YYzHndN";
    
	
    libRootcoin root(user, pw, host, port); //create new instance with listed conn-details
	    
    std::cout << "getkey: " << root.getkey(public) << std::endl;
    key = root.getkey(public);
    
    return 0;
    
    //NOTICE
    /*
    THE ABOVE CODE DOESN'T IMPLEMENT ANY KIND OF ENCRYPTION! USING THIS FORM OF 
    KEY-HANDLING CAN LEAD TO MASSIVE DAMAGE IN ANY KIND OF PRODUCTION ENVIROMENT! 
    USE SSL AND KEY-ENCRYPTION IN PRODUCTION DEPLOYMENT! FOR MORE INFOS DROP ME 
    A NOTE TO bitsta@rootcoin.co    */
}
```

build and link with librootcoin:

```
g++ rootkey.cpp -llibrootcoin
```

##License

The librootcoin library is released under the terms of [MIT](http://en.wikipedia.org/wiki/MIT_License).

```
Copyright (c) ROOTCOIN

Permission is hereby granted, free of charge, to any person obtaining a copy of 
this software and associated documentation files (the "Software"), to deal in the 
Software without restriction, including without limitation the rights to 
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of 
the Software, and to permit persons to whom the Software is furnished to do so, 
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all 
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, 
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR 
PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE 
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, 
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE 
OR OTHER DEALINGS IN THE SOFTWARE.
```
