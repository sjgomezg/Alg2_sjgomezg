PROYECTO FINAL
Algoritmos - Grupo 5

Integrantes:
  Gomez Gil, Santiago Jesus
  Gonzalez Nisperuza, Samuel
  Segura Galindo, Eduan Ferney
  
Objetivo: Implementar un algoritmo que indique la ruta con menor costo de tiempo o distancia entre dos ciudades.

Final.ipynb
  Este archivo contiene la implementación de la librería networkx, para la generación de los grafos en base a la matriz de adyacencia de tiempo de conducción y 
  distancia del recorrido obtenidos de https://co.mejoresrutas.com/tabla-de-distancias-entre-ciudades/co/, y la ejecución de los algoritmos A* (A-Star) y Dijkstra
  para encontrar la ruta más corta entre dos nodos.
  
FinalOwnImplemetation.ipynb
  Este archivo contiene la implementación que realizamos para el algoritmo Dijkstra, con el fin de encontrar la ruta más corta entre dos nodos.
  Se creo una clase llamada Dijkstra, la cual contiene los siguientes métodos:
  
    def __init__(self, vertices, graph):
        self.vertices = vertices 
        self.graph = graph
    Este método inicializa el objeto, tiene una complejidad de O(1).
    
    def find_route(self, start, end):
        unvisited = {n: float("inf") for n in self.vertices}              # O(n) 
        unvisited[start] = 0  # Vertice inicial igual a 0                 # O(1)
        visited = {}  # Lista de todos los nodos ya visitados             # O(1)
        parents = {}  # Padres de los nodos                               # O(1)
        while unvisited:                                                  # O(m) 
            # Encontrar distancia mas pequeña
            min_vertex = min(unvisited, key=unvisited.get)                # O(1)
            for neighbor, _ in self.graph.get(min_vertex, {}).items():    # O(k) 
                if neighbor in visited:                                   # O(1)
                    continue                                              
                new_distance = unvisited[min_vertex] + \                  
                    self.graph[min_vertex].get(neighbor, float("inf"))    # O(1)
                if new_distance < unvisited[neighbor]:                    # O(1)
                    unvisited[neighbor] = new_distance                    # O(1)
                    parents[neighbor] = min_vertex                        # O(1)
            visited[min_vertex] = unvisited[min_vertex]                   # O(1)
            unvisited.pop(min_vertex)                                     # O(1)
            if min_vertex == end:                                         # O(1)
                break
        return parents, visited                                           # O(1)
        
        Esta función busca la ruta con menor peso (distancia o tiempo) entre dos nodos. 
        La complejidad de esta función es O(n) + O(m) * O(k) =  O(n+m*k), donde n es el número de ciudades, m los vértices que pueden ser la ruta con menor peso y k los vértices
        adyacentes a un vértice m que son las posibles rutas a seguir.
        
        tenemos las funciones distance() y time(), que se encargan de cargar los datos de las matrices, y ambos tienen una complejidad de O(n^2).

