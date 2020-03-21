#import sys
import string
import queue
#sys.stdin = open('D:/code/ALgo_math/INP.txt', 'r')
def lis(a):
    length = 0
    result = [ 1 for i in range(len(a))]
    for i in range(1,len(a)):
        for j in range(i):
            if a[i] > a[j] and result[i] < result[j] + 1:
                result[i] = result[j] + 1
    for i in range(len(a)):
        if length < result[i]:
            length = result[i]

    return length


Q = int(input())

for tc in range(Q):
    n = int(input())
    v = list(map(int, input().split()))
    ans = 0
    for ic in range (1,10000):
        tmp = lis(v)
        #print(tmp)
        if ans < tmp:
            ans = tmp
            v = v + v
        elif ans >= tmp:
            print(ans)
            break