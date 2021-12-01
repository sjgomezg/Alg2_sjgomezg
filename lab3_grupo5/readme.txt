Laboratorio 3 - grupo 5

Integrantes:
  Gomez Gil, Santiago Jesus
  Gonzalez Nisperuza, Samuel
  Ortega Alvarado, Antonio Jose
  Segura Galindo, Eduan Ferney
  
Raíces de un polinomio por el método de la bisección.

el segmento siguiente corresponde a la función principal del código.
la complejidad es O(log(b-a)), ya que el intervalo se reduce a la mitad en cada iteración.

def biseccion(f, a, b, tol):
  c = (a + b) / 2.0           # O(1)
  x0 = f(a)                   # O(1)
  x1 = f(b)                   # O(1)
  xm = f(c)                   # O(1)
  if(x0*x1 > 0):              # O(1)
    return None, None, None   # O(1)
  iter = 0                    # O(1)
  while abs(b - a) > tol:     # O(log(b-a))
    if x0 * xm <= 0:          # O(1)
      b = c                   # O(1)
    else:         
      a  = c                  # O(1)
      x0 = xm                 # O(1)

    c = (a + b) / 2.0         # O(1)
    xm = f(c)                 # O(1)
    iter += 1                 # O(1)
  return iter, c, xm          # O(1)
                              # 7*O(1) + O(Log(b-a)) * [8*O(1)] = O(log(b-a))
