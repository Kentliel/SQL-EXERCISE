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