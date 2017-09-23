# Librería Arduino Mean Filter
La librería Mean Filter implementa un filtro de media móvil. La librería almacena los N últimos elementos de la ventana y calcula la media. Se emplea un buffer circular para mantener la eficiencia alta.

Más información https://www.luisllamas.es/libreria-arduino-quicksort/

## Instrucciones de uso
La clase Mean Filter emplea templates para permitir funcionar con distintos tipos (int, long, float,…). No obstante, hay que tener en cuenta que el filtro almacena N valores del tipo seleccionado, lo que puede causar desbordamiento si los valores filtrados y/o N son grandes. En este caso, hay que instanciar el filtro en un tipo de tamaño superior al de la señal filtrada (por ejemplo long para valores int).

### Constructor
El filtro de media móvil se instancia a través de su constructor que recibe el tamaño de la ventana como único parámetro.
```c++
MeanFilter<T> meanFilter(windowSize);
```

### Uso del filtro
```c++
// Añadir un nuevo valor al filtro y devolver el valor filtrado
meanFilter.AddValue(value);
 
//Obtiene el ultimo valor filtrado (el mismo que el devuelto al añadir el valor al filtro)
meanFilter.GetFiltered();
```


## Ejemplos
La librería Mean Filter incluye los siguientes ejemplos para ilustrar su uso.
* MeanFilterInt: Ejemplo de ordenación para variables integer.
* MeanFilterFloat: Ejemplo de ordenación para variables float.
