A* implementation for the robomaze game
=======================================

Prerequisites
-------------

You need to install `cpprest` to easily perform REST request from C++.

On Ubuntu/Debian:

```
sudo apt install libcpprest-dev
```

Installation
------------

```
mkdir build
cd build
g++ ../src/controller.cpp ../src/astar.cpp -I../include  -lcpprest -lboost_system -lcrypto -pthread -oastar
```

Usage
-----

```
./astar <name of your robot>
```

