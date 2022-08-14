# decreasing-value
# If the digit of a nonnegative integer X decreases from the largest digit to the smallest digit, it is a decreasing number. Write a program that prints the Nth decrementing number of the first line. 0 is the 0th decreasing number, 1 is the 1st decreasing number. If there is no Nth decrementing number, -1 is output. 음이 아닌 정수 X의 자릿수가 가장 큰 자릿수부터 작은 자릿수까지 감소한다면, 그 수를 감소하는 수이다. 첫번째 줄의 N번째 감소하는 수를 출력하는 프로그램을 작성하시오. 0은 0번째 감소하는 수이고, 1은 1번째 감소하는 수이다. 만약 N번째 감소하는 수가 없다면 -1을 출력한다. 
# python 

''''''''''from collections import deque #추가공부
deque_list=deque()
deque_list
for i in range(4):
    deque_list.append(i)
print(deque_list) -->deque([0, 1, 2, 3])
print(deque_list.pop()) -->3
print(deque_list.popleft()) -->0
deque_list-->deque([1, 2])'''''''''

from collections import deque
N=int(input())
total=9
d=deque(['0','1','2','3','4','5','6','7','8','9'])
if N<=9: #0은 0번째 감소 9는 9번째 감소 
    print(d[N])
    exit(0)
while d:
    c=d.popleft()
    for i in range(0,10):
        if int(c[-1])<=i:
            break
        d.append(c+str(i)) #10 20 21 30 31 32..........322,....958....
        total += 1
        if total == N: 
            print(d[-1])
            exit(0)
if(N>1022): #1023번째 감소하는 수가 없다
    print(-1)
#input--> 18
#result--> 42
