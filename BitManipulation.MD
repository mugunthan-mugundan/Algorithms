Even though these questions are rare but they do get asked sometimes.
https://www.hackerearth.com/practice/basic-programming/bit-manipulation/basics-of-bit-manipulation/tutorial/

Understand all the operations 
https://tutorialedge.net/compsci/bit-manipulation-for-beginners/

https://www.topcoder.com/community/competitive-programming/tutorials/a-bit-of-fun-fun-with-bits/

Set union
A | B
Set intersection
A & B
Set subtraction
A & ~B
Set negation
ALL_BITS ^ A
Set bit
A |= 1 << bit
Clear bit
A &= ~(1 << bit)
Test bit
(A & 1 << bit) != 0

Checking for a bit
  You can shift the number to the left and compare.
https://leetcode.com/problems/minimum-flips-to-make-a-or-b-equal-to-c

public int MinFlips(int a, int b, int c) {
        // or to get the expected value. Note or is not adding. If you have 1 and and 1 you will just get one as the or
        int val = (a|b);
        if(val == c)
            return 0;
        
        int count = 0;
        while(val > 0 || c > 0)
        {
        // check the last bit by anding with 1
            var cv = val & 1;
            var cc = c&1; 
            var aa = a &1;
            var bb = b &1;
            if(cc != cv)
            {
                // Going to zero when you have two ones take two operations.
                if(cc == 0 && aa == 1 && bb == 1)
                    count +=2;
                else
                    count++;
            }
                
            // You can continue shifting even after you reach zero.
            val = val >>1;
            c = c >>1;
            a = a >> 1;
            b = b >> 1;
            
        }
        return count;
Setting a bit
int set_bit(int position, int binary)
    // Create a bit mask based on the
    // position passed in
    // produces '10000' if we pass in position=4
    // our bit in the '4th' position is set to 1
    bit_mask = 1 << position;
    # return our binary string or-ed with our mask
    return bit_mask | binary;
    
    
