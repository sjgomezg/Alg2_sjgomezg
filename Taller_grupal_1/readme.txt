Taller grupal 1


target='AATGAATTCTCGTAACTACATAGCACAAGTAGA'
inicio = None                           #O(1)
j = 0                                   #O(1)
for i in range(0, (len(secuence)-1)):   #O(n)
  if secuence[i] == target[j]:          #O(1)
    if j == 0:                          #O(1)
      inicio=i #O(1)
    if j == len(target) -1:             #O(1)
      print(inicio, i)                  #O(1)
      j = 0                             #O(1)
    j += 1                              #O(1)
  else: #O(1)
    j = 0                               #O(1)
                                        #O(1)+O(1)+O(n[O(1)+O(1)+O(1)+O(1)+O(1)+O(1)+O(1)+O(1)+O(1)]) = O(n)

El segmento anterior muestra el codigo que ese utilizó para encontrar la cadena target en el string secuence.
Frente a cada operción se especifica su complejidad, y al final el resultado de estas.
