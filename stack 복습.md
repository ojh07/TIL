![image-20220222090317440](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220222090317440.png)

스택, 재귀호출까지만 거의 출제



![image-20220222094202591](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220222094202591.png)





memoization

사람이 하듯이 중복으로 함수를 호출하지 않고 구할 수 있도록

![image-20220222100437912](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220222100437912.png)

이런식이면 중복호출이 많아지면서 매우 느려진다

![image-20220222100632824](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220222100632824.png)

memoization을 이용한 프로그래밍 방법이 DP알고리즘이다

크기가 작은 부분을 모두 해결한 후 DP Arr에 적어놓고 그 적어놓은것을 활용해서 다음 부분을 해결해나가는것

바로 전이 최적해이므로 그 전에있는 것들은 신경쓰지 않는다(그 전에있는 것들도 앞에것들의 최적해이기 때문)



![image-20220222101334111](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220222101334111.png)





DFS는 그래프와 트리구조를 먼저 알아야한다







<파스칼의 삼각형 풀이>

memoization 이용한 방법

![image-20220222125845960](stack%20%EB%B3%B5%EC%8A%B5.assets/image-20220222125845960.png)





<피보나치>

```python
# 1 recursive
def fibo(n):
    if n < 2:
        return n
    else:
        return fibo(n - 1) + fibo(n - 2)


print(fibo(10))


# 2 memoization 사용
def fibo_memo(n):
    global memo
    if n >= 2 and len(memo) <= n:
        memo.append(fibo_memo(n - 1) + fibo_memo(n - 2))
    return memo[n]


memo = [0, 1]

print(fibo_memo(10))
```