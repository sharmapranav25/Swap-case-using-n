# Swap-case-using-n
change the given string s using a non-negative integer n.

Each bit in n will specify whether or not to swap the case for each alphabetic character in s: if the bit is 1, swap the case; if its 0, leave it as is. When you finish with the last bit of n, start again with the first bit.

You should skip the checking of bits when a non-alphabetic character is encountered, but they should be preserved in their original positions.

## Examples
swap("Hello world!", 11) --> "heLLO wORLd!" ...because 11 is 1011 in binary, so the 1st, 3rd, 4th, 5th, 7th, 8th and 9th alphabetical characters have to be swapped:

H e l l o w o r l d ! 1 0 1 1 1 x 0 1 1 1 0 x ^ ^ ^ ^ ^ ^ ^

## More examples
swap("gOOd MOrniNg", 7864) --> "GooD MorNIng" swap("", 11345) --> "" swap("the lord of the rings", 0) --> "the lord of the rings"

# Code

    def swap(s,n):
        strg=""
        iter_n= iter(bin(n)[2:])
        def switchcase(string):
            if ord(string) in range(65, 91):
                string= string.lower()
            else:
                string= string.upper()
            return string
        for i in s:
            if ord(i) in range(65, 91) or ord(i) in range(97,123):
                try:
                    temp= int(next(iter_n))
                    if temp == 1:
                        strg = strg + switchcase(i)
                    else:
                        strg= strg + i
                except:
                    iter_n= iter(bin(n)[2:])
                    temp= int(next(iter_n))
                    if temp == 1:
                        strg= strg + switchcase(i)
                    else:
                        strg= strg + i
            else:
                strg= strg + i
        return print(strg)
        
        
    #test cases
    swap('pranav', 9)
    swap('pranav', 1)
    swap('siddharth', 2)
    swap("",9)


# Output


    PraNAv
    PRANAV
    SiDdHaRtH




