# nymph ![logo](http://icons.iconarchive.com/icons/iron-devil/ids-game-world/32/Fairy-icon.png)
Let's see what we can achieve by reworking C syntax.

## Updates
A new parser has been implemented.

Default object member values implemented.

Function overloading implemented!

## Goals

Namespace?

## Example
box.n

    #include <stdlib.h>
    #include <stdio.h>

    obj Box {
        int height = 1;
        int width = 1;
        int depth = 1;
    }

    int add(int a, int b) {
      return a + b;
    }

    pub void print(Box *this) {
        printf("%i %i %i\n",1+add(2+this->height+2, this->height)+2, 2+this->width+2, this->depth);
    }

rect.n

    #include <stdlib.h>
    #include <stdio.h>

    obj Rect {
        int height = 3;
        int width = 3;
    }

    pub void print(Rect *this) {
        printf("%i %i\n", this->height, this->width);
    }

main.n

    #include <stdlib.h>
    #include "box.n"
    #include "rect.n"

    int main(int argc, const char * argv[]) {

        Box **myBoxes = new Box*10;
        Box *myBox = new Box;
        myBoxes[0] = myBox;
        Rect *myRect = new Rect;

        print(myBoxes[0]);
        print(myRect);

        free(myBox);
        free(myBoxes);
        free(myRect);

        return 0;
    }

makefile
```make
    nymph: nymph_compiler.c box.n rect.n main.n
            gcc -std=c11 nymph_compiler.c -o nymph
            ./nymph main.n main
            gcc -std=c11 -c box.c box.h
            gcc -std=c11 -c rect.c rect.h
            gcc -std=c11 -c main.c main.h
            gcc -std=c11 main.o box.o rect.o -o out
```
