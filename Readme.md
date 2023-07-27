Vamos a trabajar con nuestra primera base de datos de SQL. Crea una base de datos nueva llamada `building`:

### [](https://github.com/GammaTechSchool/MAD_PART_JsCao_1/blob/main/src/backend/exercises/sql1.md#ejercicio-1)Ejercicio 1

1. Tabla `apartments` con las siguientes columnas:
    - `apartment_id`: primary key, serial.
    - `name`: string (ej: `2ºB, 5ºA`, etc).
    - `rooms`: int (número de habitaciones).
    - `bathrooms`: int (número de baños).
    - `area`: numeric (metros cuadrados).

```SQL 
    CREATE TABLE apartments(
	apartment_id INTEGER PRIMARY KEY,
	name CHAR,
	rooms INTEGER,
	bathrooms INTEGER,
	area NUMERIC
    );
```

2. Tabla `families` con las siguientes columnas:
    - `family_id`: primary key, serial.
    - `name`: string.
    - `members`: int (número de miembros).
    - `apartment`: int (`id` de la tabla `apartments`).

```SQL
CREATE TABLE families (
	family_id INTEGER PRIMARY KEY,
	name CHAR,
	members INTEGER,
	apartment INTEGER,
	CONSTRAINT fk_apartments
		FOREIGN KEY(apartment)
			REFERENCES apartments(apartment_id)
);
```

### [](https://github.com/GammaTechSchool/MAD_PART_JsCao_1/blob/main/src/backend/exercises/sql1.md#ejercicio-2)Ejercicio 2

Introduce `5` filas en la tabla de `apartments` y de `families`, con los datos que quieras.

### [](https://github.com/GammaTechSchool/MAD_PART_JsCao_1/blob/main/src/backend/exercises/sql1.md#ejercicio-3)Ejercicio 3

Realiza las siguientes consultas a la base de datos:

1. Obtén todas filas y columnas de la tabla `families`.
2. Obtén los nombres de todas las familias de `families`.
3. Obtén todos los pisos de la tabla `apartments` que tengan más de 2 habitaciones.
4. Obtén todos los nombres de los pisos de la tabla `partaments` que tengan más de `100` metros cuadrados y más de `3` habitaciones.
5. Obtén el número de miembros de las familias que tengan más de `2` miembros, y ordena los resultados de menor a mayor.
6. Obtén el nombre de los apartamentos que tengan `2` o más baños, o `2` o más habitaciones.
7. Obtén los nombres de las familias que vivan en pisos de menos de `3` habitaciones.
8. Obtén todas las columnas de las familias que vivan en pisos de más de `74` metros cuadrados.
9. Obtén el nombre de los pisos que tengan más de `2` inquilinos.
10. Obtén el nombre de los pisos que tengan menos de `3` inquilinos y más de `2` habitaciones.