# grahics.h-linux
A quick walkthrough in how to integrate graphics.h library to gcc compiler in linux

## The following steps needed to be done(mostly copy-paste):
1. Clone this repository (Type `git clone https://github.com/khaledCSE/grahics.h-linux.git` and press ENTER).
2. Go to the folder named `libgraph-1.0.2` inside it and open a terminal there.
3. Type `sudo add-apt-repository universe` and press ENTER
4. Type `sudo apt update` and press ENTER
5. Type `sudo nano /etc/apt/sources.list` and press ENTER
6. Add the following lines there:
    `deb http://us.archive.ubuntu.com/ubuntu/ xenial main universe` and
    `deb-src http://us.archive.ubuntu.com/ubuntu/ xenial main universe`
7. Press CTRL+X and then press Y and press ENTER
8. Now Add this line to the terminal:
    `sudo apt-get install libsdl-image1.2 libsdl-image1.2-dev guile-1.8 guile-1.8-dev libsdl1.2debian libart-2.0-dev libaudiofile-dev libesd0-dev libdirectfb-dev libdirectfb-extra libfreetype6-dev libxext-dev x11proto-xext-dev libfreetype6 libaa1 libaa1-dev libslang2-dev libasound2 libasound2-dev` and press ENTER.
9. Type `./configure` and press ENTER
10. Type `make` and press ENTER
11. Type `sudo make install` and press ENTER
12. Type `sudo cp /usr/local/lib/libgraph.* /usr/lib` and press ENTER
13. Done! You can try the following code for testing: (type `xed demo.cpp` and press ENTER):
    ```#include<stdio.h> 
       #include<stdlib.h> 
       #include<graphics.h> 
       int main() 
       { 
            int gd = DETECT, gm; 
            initgraph(&gd, &gm, NULL); 
  
            circle(50, 50, 30); 
  
            delay(500000); 
            closegraph(); 
            return 0; 
        }
14. Save it as `demo.cpp` and close the editor.
15. Type `gcc demo.cpp -o demo -lgraph` and ENTER.
16. You should see the output by now.