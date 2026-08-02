# Optimización no lineal

Implementación en Python de un método de gradiente conjugado no lineal para minimizar funciones diferenciables de varias variables.

El código permite definir una función objetivo y su gradiente, calcular una dirección de descenso y aproximar el tamaño del paso mediante una búsqueda lineal.

## Método utilizado

Se utiliza el método de **gradiente conjugado no lineal de Hestenes–Stiefel**, con reinicio cuando la dirección calculada deja de ser conveniente.

En cada iteración se actualiza

```text
x_(k+1) = x_k + alpha_k d_k
```

El valor `alpha_k` se obtiene mediante una búsqueda lineal basada en el método de la secante aplicado a la derivada direccional.

El algoritmo termina cuando la norma del gradiente es menor que la tolerancia solicitada o cuando se alcanza el máximo de iteraciones.

## Funciones principales

- `funcion_objetivo`: función que se desea minimizar.
- `gradiente`: gradiente de la función objetivo.
- `derivada_direccional`: derivada de la función sobre una dirección.
- `metodo_secante`: búsqueda aproximada del tamaño del paso.
- `gradiente_conjugado`: ejecución del algoritmo principal.

## Ejecución

Instalar las dependencias:

```bash
python -m pip install numpy matplotlib
```

Ejecutar el archivo principal:

```bash
python optimizacion_no_lineal.py
```

Para probar otra función se deben modificar `funcion_objetivo` y `gradiente`, manteniendo la misma cantidad de variables.

Ejemplo de punto inicial:

```python
x0 = np.array([1.0, 1.0])
```

## Resultados

El programa entrega, según la versión utilizada:

- punto aproximado de mínimo;
- valor de la función objetivo;
- norma final del gradiente;
- cantidad de iteraciones;
- trayectoria seguida por el algoritmo.

## Limitaciones

- Se requiere disponer del gradiente de la función.
- La convergencia depende del punto inicial y de la búsqueda lineal.
- No se consideran restricciones sobre las variables.
- El método puede detenerse en un mínimo local o en un punto estacionario.
- No está pensado para funciones no diferenciables.

## Tecnologías

- Python
- NumPy
- Matplotlib
