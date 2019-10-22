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
g++ controller.cpp astar.cpp  -lcpprest -lboost_system -lcrypto -pthread -oastar
```

Usage
-----

```
./astar <name of your robot>
```

