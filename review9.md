# 1월19일_1

## [실습1]

![image-20210131012916758](C:\Users\jinsujeong\AppData\Roaming\Typora\typora-user-images\image-20210131012916758.png)

```python
class Member:
    def __init__(self):
        self.name = None
        self.account = None
        self.passwd = None
        self.birthyear = None


s1 = Member()
s2 = Member()
s3 = Member()

s1.name = "kim"
s1.account = "abc"
s1.passwd = "ABC"
s1.birthyear = 1996

s2.name = "lee"
s2.account = "def"
s2.passwd = "DEF"
s2.birthyear = 1997

s3.name = "park"
s3.account = "ghi"
s3.passwd = "GHI"
s3.birthyear = 1998

print(f"회원1 : {s1.name}({s1.account}, {s1.passwd}, {s1.birthyear})")
print(f"회원2 : {s2.name}({s2.account}, {s2.passwd}, {s2.birthyear})")
print(f"회원3 : {s3.name}({s3.account}, {s3.passwd}, {s3.birthyear})")
```

회원1 : kim(abc, ABC, 1996)
회원2 : lee(def, DEF, 1997)
회원3 : park(ghi, GHI, 1998)

## [실습2]

![image-20210131013124091](C:\Users\jinsujeong\AppData\Roaming\Typora\typora-user-images\image-20210131013124091.png)

```python
class Book:
    def __init__(self, title, author, price):
        self.title = title
        self.author = author
        self.price = price

    def getBookInfo(self):
        return f"{self.title},{self.author},{self.price}"


Book1 = Book('파이썬 정복', '김상형', 22000)
Book2 = Book('부의 대이동', '오건영', 17000)
Book3 = Book('보통의 언어들', '김이나', 14500)
Book4 = Book('아몬드', '손원평', 12000)
Book5 = Book('코스모스', '칼 세이건', 18500)


def printBookInfo(book):
    bookInfo = book.getBookInfo().split(',')
    for i in range(0, 3):
        print(bookInfo[i])
    print('-'*10)

printBookInfo(Book1)
printBookInfo(Book2)
printBookInfo(Book3)
printBookInfo(Book4)
printBookInfo(Book5)
```

파이썬 정복
김상형

22000

부의 대이동
오건영

17000

보통의 언어들
김이나

14500

아몬드
손원평

12000

코스모스
칼 세이건

18500

```python
class Book:
    def __init__(self, title="파이썬 정복", author="김상형", price=22000):
        self.title = title
        self.author = author
        self.price = price

    def getBookInfo(self):
        return f"{self.title},{self.author},{self.price}"

b1 = Book()
b2 = Book("생활코딩! HTML+CSS+자바스크립트", "이고잉", 27000)
b3 = Book("돈을 부르는 작은 습관", "공형조", 15800)
b4 = Book("기억1", "베르나르 베르베르", 14800)
b5 = Book("적당히 가까운 사이", "댄싱스네일", 14500)

for i in [b1, b2, b3, b4, b5]:
    print(i.getBookInfo().replace(",", "\n"))
    print("-" * 10)
```

```python
class Book:
    store = "yes24" # 클래스변수
    def __init__(self, title, author, price):
        self.title = title      # 인스턴스변수
        self.author = author    # 인스턴스변수
        self.price = price      # 인스턴스변수

    def getBookInfo(self):
        info = self.title + ',' + self.author + ',' + str(self.price)
        return info

book1 = Book("파이썬 정복", "김상형", 22000)
book2 = Book("이것이 MariaDB다", "우재남", 30000)
book3 = Book("파이썬 웹프로그래밍", "김석훈", 22000)
book4 = Book("맛있는 MongoDB", "정승호", 28000)
book5 = Book("생활코딩! HTML+CSS+자바스크립트", "이고잉", 27000)

list = [book1, book2, book3, book4, book5]
cnt = 0
for info in list:
    print(info.getBookInfo().replace(',', '\n'))
    cnt = cnt+1
    if cnt<5:
        print('-'*9)
```