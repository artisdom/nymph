# nymph
A slightly different version of C.


In Nymph, String means char \*.

In Nymph, ADTs and primitive data types functions are simplified.


Simply compile your nymph \*.c file with ./nymph \<file to compile into c\> \<output name\>

Example program:

File: test_nymph.c

    #include <stdio.h>

    int int.myWorld(String a,float b) { //primitive data type function declaration
        printf("%s %f", a, b);
        return this;
    }

    void String.world(int b,int c) { //object function declaration
        printf("%c%c\n", this[b], this[c]); //"this" is the string object
    }

    int main(int argc, const char * argv[]) {

        String hello = "Blah";
        int blade = 1;
        int runner = 2;

        blade.myWorld(hello,(float)runner); //calling primitive data type function

        hello.world(blade,runner); //calling object function

        return 0;
    }
