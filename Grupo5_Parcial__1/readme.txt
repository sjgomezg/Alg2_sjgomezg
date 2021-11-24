Parcial 1 - Grupo 5

Integrantes:
  Gomez Gil, Santiago Jesus
  Gonzalez Nisperuza, Samuel
  Ortega Alvarado, Antonio Jose
  Segura Galindo, Eduan Ferney
 
Algoritmo #1 - Multiplicacion de dos entereos por el metodo de "La Russe"
  
  En el sisguiete segmento de codigo se evidencia funcion con la cual se calcula el producto de los dos enteros. 
  Se utiliza el desplazamiento de bits para la multiplicacion y divicion por 2 correspondientes.
  Frente a cada linea se especifica la complejidad de la operacion y al final el resultado.
  
  def productTwoIntegers(a, b): #Definimos la funciona que calculara el producto de dos enteros
  result = 0                        #O(1)
  while(b > 0):                     #O(log(b))
    if(b & 1): result = result + a  #O(1)
    a = a << 1                      #O(1)
    b = b >> 1                      #O(1)
  return result                     #O(1)
                                    #O(n)=O(1)+ O(log(n))*[ O(1)+O(1)+O(1) ] +0(1) = O(log(b))
                                    
 Algoritmo #2 - Calculo del n-ésimo numero de la serie de Fibonacci
  
  En el sisguiete segmento de codigo se evidencia funcion con la cual se calcula n-ésimo numero de la serie de Fibonacci. 
  Frente a cada linea se especifica la complejidad de la operacion y al final el resultado.
  
  def fibonacciNumber(n): 
  a = 0                   #O(1)
  b = 1                   #O(1)
  c = 0                   #O(1)
  if(n == 0):             #O(1)
    return a              #O(1)
  else:                   #O(1)
    for i in range(1,n):  #O(1)
      c = a + b           #O(1)
      a = b               #O(1)
      b = c               #O(1)
    return c              #O(1)
                          #O(n) = O(1)+O(1)+O(1)+O(1)+O(1)+O(1)+O(1)+ O(n)*[ O(1)+O(1)+O(1) ] + O(1) = O(n)
