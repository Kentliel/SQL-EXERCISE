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
	name TEXT,
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
	name TEXT,
	members INTEGER,
	apartment INTEGER,
	CONSTRAINT fk_apartments
		FOREIGN KEY(apartment_id)
			REFERENCES apartments(apartment_id)
);
```

### [](https://github.com/GammaTechSchool/MAD_PART_JsCao_1/blob/main/src/backend/exercises/sql1.md#ejercicio-2)Ejercicio 2

Introduce `5` filas en la tabla de `apartments` y de `families`, con los datos que quieras.

```sql
INSERT INTO apartments (apartment_id, name, rooms, bathrooms, area)
VALUES
(1, 'Alfred', 2, 1, 70.20),
(2, 'Jessica', 3, 2, 100.30),
(3, 'Fiorella', 2, 2, 90.40),
(4, 'Jesus', 4, 2, 110.10),
(5, 'Margot', 3, 3, 120.50)
RETURNING *;
```
![](https://i.imgur.com/ZJonyM3.png)

```SQL
INSERT INTO families (family_id, name, members, apartment)
VALUES
(10, 'Arellano', 2, 1),
(11, 'Chacón', 3, 2),
(12, 'Contreras', 2, 3),
(13, 'Carretto', 4, 4),
(14, 'Medina', 3, 5)
RETURNING *;
```
![](https://i.imgur.com/iO23U9Q.png)
### [](https://github.com/GammaTechSchool/MAD_PART_JsCao_1/blob/main/src/backend/exercises/sql1.md#ejercicio-3)Ejercicio 3

Realiza las siguientes consultas a la base de datos:

1. Obtén todas filas y columnas de la tabla `families`.

![](https://i.imgur.com/UWTR5oD.png)

2. Obtén los nombres de todas las familias de `families`.

![](https://i.imgur.com/6JWTFlZ.png)

3. Obtén todos los pisos de la tabla `apartments` que tengan más de 2 habitaciones.

![](https://i.imgur.com/BUf2E7K.png)

4. Obtén todos los nombres de los pisos de la tabla `apartaments` que tengan más de `100` metros cuadrados y más de `3` habitaciones.

![](https://i.imgur.com/UIy9KRY.png)

5. Obtén el número de miembros de las familias que tengan más de `2` miembros, y ordena los resultados de menor a mayor.

![](https://i.imgur.com/NsKzubh.png)

6. Obtén el nombre de los apartamentos que tengan `2` o más baños, o `2` o más habitaciones.

![](https://i.imgur.com/0A79f4k.png)

7. Obtén los nombres de las familias que vivan en pisos de menos de `3` habitaciones.  

![](https://i.imgur.com/fvGMVk2.png)

8. Obtén todas las columnas de las familias que vivan en pisos de más de `74` metros cuadrados.

![](https://i.imgur.com/nVwo1cO.png)

9. Obtén el nombre de los pisos que tengan más de `2` inquilinos.

![](https://i.imgur.com/nwWDQeL.png)

10. Obtén el nombre de los pisos que tengan menos de `3` inquilinos y más de `2` habitaciones.

![](https://i.imgur.com/Wcfd9o2.png)