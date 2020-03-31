# Euclid's Algorithm - Öklid Algoritması

Öklid algoritması, Shor algoritmasında kullanılan bir yöntemdir. İki sayının en büyük ortak bölenini bulur.
A ve B sayılarımız olsun.
A*A*A*A*A*A... = x*B+1
A^p = x*B+1 kısmı Shor algoritmasında işimize yarayan kısımdır.

#Örnek:
270 ve 192'nin OBEB'ini bulun
A=270, B=192
A ≠0
B ≠0
Bölme yapılarak, bölüm 270/192 = 1 ve kalan 78 olarak bulunr. Bu işlemi 270 = 192 * 1 +78 şeklinde de yazabiliriz
OBEB(270,192)=OBEB(192,78) olduğu için OBEB(192,78)'i bulun
A=192, B=78
A ≠0
B ≠0
Bölme yaparak, bölüm 192/78 = 2 ve kalan 36 olarak bulun. Bunu şöyle yazabiliriz:
192 = 78 * 2 + 36
OBEB(192,78)=OBEB(78,36) olduğu için, OBEB(78,36)'yı bulun
A=78, B=36
A ≠0
B ≠0
Bölme yapılarak, bölüm 78/36 = 2 ve kalan 6 olarak bulun. Bunu şöyle yazabiliriz:
78 = 36 * 2 + 6
OBEB(78,36)=OBEB(36,6) olduğu için, OBEB(36,6)'yı bulun
A=36, B=6
A ≠0
B ≠0
Bölme yapılarak, bölüm 36/6 = 6 ve kalan 0 olarak bulunur. Bunu şöyle yazabiliriz:
36 = 6 * 6 + 0
OBEB(36,6)=OBEB(6,0) olduğu için, OBEB(6,0)'yı bulun
A=6, B=0
A ≠0
B =0, OBEB(6,0)=6
Böylece şunu göstermiş olduk:
OBEB(270,192) = OBEB(192,78) = OBEB(78,36) = OBEB(36,6) = OBEB(6,0) = 6
OBEB(270,192) = 6

Example Source:khanacademy.org