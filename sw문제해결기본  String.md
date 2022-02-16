# sw문제해결기본 : String



![image-20220216090152435](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216090152435.png)

컴퓨터에서의 문자표현

각 문자에 대해 대응되는 숫자에 정해놓고 이것을 메모리에 저장

영어 대소문자 합쳐서 52라서 6비트(2**6=64)면 모두 표현가능



표준아스키는 7비트로 표현

확장 아스키는 8비트를 모두 사용하면서 추가적인 문자표현



아스키코드에서 A는 65, a는 97 이라는것만 알고있자



다국어 처리를 위한 표준 - 유니코드

8-bit  8bits 는 같은뜻

표준은 무조건 원본, 공식사이트 기준으로해야함

바이트 순서에 대해서 표준화하지 못했다..?

endian (big-dendian, little-endian)

바이트단위로 메모리에서 주소를 기록

낮은자리수를 빠른주소에 저장 - little endian



![image-20220216093857681](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216093857681.png)



![image-20220216094032502](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216094032502.png)

![image-20220216094231386](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216094231386.png)



print() 해주면 빈칸나오면서 줄바꿈!

문자열은 튜플과 같이 요소값을 변경불가(immutable)

리스트형태면 하나씩 꺼내서 수정하기도 쉬움

문자열 길이의 절반만큼 횟수가 필요함(문자열 뒤집기를 위해서는)

![image-20220216140224257](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216140224257.png)



reverse는 리스트로 저장햇을 때 사용가능

```python
문자열뒤집기
# 문자열 뒤집기
# 1. 슬라이싱 사용
my_str = "abc"
my_str = my_str[::-1]
print(my_str)

# 2. reverse 메소드를 사용하고싶다
my_str = "abc"
my_str = list(my_str)
my_str.reverse()
my_str = "".join(my_str)
print(my_str)

# 3. 새로운 문자열 생성
new_str = ""
my_str = "abc"
for ch in my_str:
    new_str = ch + new_str
print(new_str)
```





a<b 라고 했을때 문자열이면 b가 a보다 앞서 적어져있냐고 물어보는것( 기준이 유니코드임 유니코드 참조해야한다)





패턴매칭

![image-20220216104937780](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216104937780.png)

<고지식한 알고리즘>

![image-20220216110546134](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216110546134.png)

![image-20220216111027577](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216111027577.png)

j는 -1로 되돌리고 다시 +1을 해줘서 0부터 시작

![image-20220216111547331](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216111547331.png)



<kmp 알고리즘>

![image-20220216111726195](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216111726195.png)

시간복잡도: O(M+N)

아이디어만 참고해보기

https://bowbowbow.tistory.com/6

패턴을 찾아서 뛰어넘을때 일치하는 패턴을 인덱스로 앞부분을 맞춰준다..?

내가 찾으려는 문자열안에 패턴이 있다면 abcdabc가 있을때 abc abc 같으니까 뒤에거로 뛰어넘자

불일치한 곳 인덱스가 앞에 일치하는것의 개수..?

스킵 배열을 만드는방법, 스킵배열을 활용하는방법만 할 수 있어도 괜찮음(+ 구글링)



<보이어-무어 알고리즘>

어떤방식으로 진행되는지만 알면된다

오른쪽부터 비교해서 내가 검색하고자 하는 문자열에 없으면 그 문자열 길이만큼 한번에 점프

![image-20220216164243007](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216164243007.png)



![image-20220216144621186](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216144621186.png)

**코드로는 고지식한 패턴알고리즘만 구현할 수 있으면 된다**



빅O는 최악의경우

세타는 세타는 최악의 경우와 최선의 경우가 같은 증가율일 때 하나로 퉁쳐서 표현하기 위해 사용

![image-20220216144810893](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216144810893.png)

보이어-무어와 비슷하게 사용하고 싶다면 너무 복잡하기 때문에 호스풀 알고리즘을 사용하면된다(horspool)



<문자열 암호화>

![image-20220216165517158](sw%EB%AC%B8%EC%A0%9C%ED%95%B4%EA%B2%B0%EA%B8%B0%EB%B3%B8%20%20String.assets/image-20220216165517158.png)

이런 문제낼수도

![image-20220216165544603](sw%EB%AC%B8%EC%A0%9C%ED%95%B4%EA%B2%B0%EA%B8%B0%EB%B3%B8%20%20String.assets/image-20220216165544603.png)

두개가 다를때 1, 같으면 0 

왼쪽 표를 활용해서 암호화를 하는것(평문과 암호문을 왔다갔다할수있다) ---- **서술형가능할수도**

xor이 1이면 원래 0이면 1로바꾸고 1이면 0으로바꿈(토글)





![image-20220216150903825](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216150903825.png)

![image-20220216150918302](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220216150918302.png)

```python
import sys
sys.stdin = open("input.txt")

T = int(input())

for tc in range(1, T+1):
    n = int(input())
    num_list = list(map(int,input()))
    cnt = 0
    cnt_max = 0
    for num in num_list:
        if num == 1:
            cnt += 1
            if cnt > cnt_max:
               cnt_max = cnt
        else:
            cnt = 0
    print(f'#{tc} {cnt_max}')
```

고대유적 ---- 위의 버전의 가로세로 다있는버전(아마도 매트릭스 만들어서 가로세로 둘다세주고 1같이 있는거 +해줘야할듯)

