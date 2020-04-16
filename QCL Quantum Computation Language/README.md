# QCL Quantum Computing Language - Kuantum Hesaplama Dili

QCL, klasik bilgisayarlarda kuantum hesaplamalarını test edebileceğiniz bir dildir.
C ile yazılmıştır. Hadamard kapısı gibi birçok kuantum kapısı kullanılabilir.

qureg: kuantum register tanımlama:

qureg x[1] // 1 qubiti x adındaki değişkene allocate ediyoruz.

dump // State'i (durumları) listeler.

Not(x) // x değişkenini not kapısına tabii tutar. (Örn: 1|0> ise 1|1> olur)

H(x) // x değişkenini hadamard kapısına tabii tutar. (Örn: 1|0> ise 0.70711 |0> + 0.70711 |1> ) (0.70711 = 1/sqrt(2))

Daha detaylı bilgi için: https://en.wikipedia.org/wiki/Quantum_Computation_Language