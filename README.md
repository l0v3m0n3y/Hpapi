# Hpapi
api for hp-api.onrender.com site about Harry Potter fandom
# main
```cpp
#include "Hpapi.h"
#include <iostream>

int main() {
   Hpapi api;

    auto characters = api.characters_list().then([](json::value result) {
        std::cout << "Search results: " << result.serialize() << std::endl;
    });
    characters.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
