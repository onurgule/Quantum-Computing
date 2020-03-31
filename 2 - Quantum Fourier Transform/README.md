# Quantum Fourier Transform - Kuantum Fourier Dönüşümü

Kuantum Fourier Dönüşümü, qubitlerin verilen k değerine göre tüm süperpozisyonlarındaki değişimlerini görebildiğimiz bir uygulamadır.
QFT olarak gösterilir.

QFTk : |Z> => 1/sqrt(2^k)∑exp(2πi*Z*b/2^k)|b>

Örnek:
|1> -> QFT -> 7|1> + 0|2> + -7|3> + -1|4> + -7|5> + ...
Kuantum Fourier Dönüşümüne verdiğimiz değeri yükseltirsek;
|2> -> QFT -> 0|1> + 1|2> + 0|3> + 1|4> + ...
spektrum frekansı artacaktır.

Bunları toplarsak;
|1> + |2>
ve QFT'e uğratırsak;
|1>+|2> -> QFT -> (1/aradaki fark)'ı bize verecektir.
Bu aradaki fark, Shor's algoritmasında çok önemli olarak kullanılır.