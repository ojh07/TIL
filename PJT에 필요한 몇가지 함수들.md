## PJT에 필요한 몇가지 함수들

JSON -> 데이터를 표현하는 방법중 하나    java script object notation

key, value로 이루어짐

데이터를 읽는 방법을 알아야함..



가벼운 데이터 교환 방식



open(파일의 경로, 어떤모드로 열어줄까(쓰기'w', 읽기'r', 수정'a'), encoding = 'UTF-8',    아스키 등 여러가지 있음)



open  ----- > 파일을 읽어오는 것 

opne을 하고 파일을 다 썼으면 close 해줘야함

readline 한줄읽고 기다리고 한줄일고 기다리고(for , while과 함께 쓰임)

readlines 파일 처음부터 끝까지 다 읽음

json.node(오픈한 파일 넣어주는곳)





원소가 딕셔너리인 리스트    key : value 한칸뛰고 key: value 형태로 출력..

반복문

for each_dict in data:

  title = each_dict['title']

  year = each_dict['year']

  print(f"제목: {title} 개봉년도: {year}")

------> 예시



![image-20220120150636417](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220120150636417.png)



open close 같이 안쓰는대신 with 써도됨!!

![image-20220120150906594](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220120150906594.png)



``` python
with open('data/data.json', 'r', encoding='UTF-8') as file_stream:
    data = json.load(file_stream)
    for each_dict in data:
        title = each_dict['title']
        year = each_dict['year']
        print(f'제목: {title} 개봉년도: {year}')
```





![image-20220120151229477](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220120151229477.png)

### ------->월말평가 예시

pass는 지우고 시작하면됨

정의는 되어있는데 로직이 없으니까 로직 채우는 형식

중간에 코드 작성

조건 없으면 함수 사용은 자유!!



예상문제 풀어볼 수 있음!!!

###### 과락 기준 -> 문제가 나와야 알 수 있음