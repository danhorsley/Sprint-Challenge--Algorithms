#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) This first algorithm goes up linearly with n.  The first few iterations are as follows:
        a0 = 0
        a1 = n^2
        a2 = n^2 + n^2 = 2n^2
   So we can generalize for the nth iteration
        an = n*(n^2) = n^3
   This will be the first time the while condition fails, i.e we've taken exactly n loops to break the cycle.
   So number of loops and hence run-time goes up linearly with n.


b) This one is a little trickier as you need 2^j to be greater than n for every i in the range 0 to n.  Each individual loop takes log to base 2 of n loops rounded up to breach the n limit.  as n gets larger and larger teh rouding up becomes more and mroe insignificant. Then you need to multiply that by n for each 'i' loop.  so for larger n the answer is n*log_base_2(n)



c) This loop is recursive and requires a trigger to break of bunnies = 0.  as the number of initial bunnies go up it takes longer each time but only linearly as all the recusion done is count backwards by one.  So for bunnies equal 50 for example it takes exactly 50 loops to break and for the recused bunny to equal 0 (giving an answer of 2* intiial bunnies)

## Exercise II

This would be an ideal time to use a binary style search!  First of all go half way up the building and see if the egg breaks.  Then depending on whether it breaks or not concentrate your search on the lower or upper half and repeat recursively (breaks - go lower, doesn't break go higher).

Binary searches run in log(n) time.

here's some example python
f = 46
n = 100
floor_list = [x for x in range(n)]
def find_my_f(fl = floor_list):
    print(fl)
    if len(fl)<=3:
        for floor in fl:
            if floor==f:
                return floor
    low = 0
    high = len(fl)
    mid = high//2
    if fl[mid] >= f:  #condition breaks
        ret = find_my_f(fl[low:mid+1])
        return ret
    if fl[mid] < f: #conditions doesn't break
        ret = find_my_f(fl[mid+1:high])
        return ret




