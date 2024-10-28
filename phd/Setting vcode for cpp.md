# 1. installation of compilers
This will update and install the gcc and g++

```
sudo apt update
sudo apt install build-essential
```

To test the command 
```
gcc --version
g++ --version
```

To check lets create a 
```
# create a new folder work and open in the vscode
mdkir work
code ./work
```

# 2 Install extension
Go to extension and install the following:
1. C/C++ extension from microsoft

# 3. create a simple prog
```cpp
// create a code to print 1 to 10

#include <iostream>

using namespace std;

  

int main() {

for (int i = 1; i <= 10; i++) {

cout << i << endl;

}

return 0;

}
```

# 4.  to compile and rund
run cpp file in the small arrow 
![[Pasted image 20241002190057.png]]