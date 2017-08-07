# nymph ![logo](http://icons.iconarchive.com/icons/iron-devil/ids-game-world/32/Fairy-icon.png)
A slightly different version of C.
<br/>
<br/>
In Nymph, String means char \*.

In Nymph, ADTs and primitive data type functions are simplified.

In Nymph, terminators are not semicolons, but newlines.
<br/>

    #include <stdio.h>

    void String.world(int b,int c) { //object function declaration
        printf("%c%c\n", this[b], this[c]) //"this" is the string object
    }

    int main(int argc, const char * argv[]) {

        String hello = "Blah"
        int blade = 1
        int runner = 2

        hello.world(blade,runner) //calling object function

        return 0
    }
