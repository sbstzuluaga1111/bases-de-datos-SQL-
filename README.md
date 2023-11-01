# bases-de-datos-SQL-

```
CREATE DATABASE campus;
USE campus;
CREATE TABLE estudiantes(
    id_estudiante INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    edad INT
);
CREATE TABLE notas(
    id_nota INT PRIMARY KEY AUTO_INCREMENT,
    id_estudiante INT,
    aignatura VARCHAR(50),
    calificacion INT,
    FOREIGN KEY (id_estudiante) REFERENCES estudiantes(id_estudiante)
);
-- Comandos DDL
ALTER TABLE estudiantes ADD COLUMN email VARCHAR(50);
ALTER TABLE notas MODIFY COLUMN calificacion FLOAT;
DROP TABLE notas;

-- Comandos DML

INSERT INTO estudiantes (id_estudiante, nombre, apellido, edad)
VALUES (1, "juan", "perez", 18),
(2, "maria", "gomez", 20),
(3, "carlos", "rodriguez", 19)
;

INSERT INTO notas (id_nota, id_estudiante, aignatura, calificacion)
VALUES (1, 1, "Matematicas", 5.0),
(2, 2, "Ciencias", 4.0),
(3, 3, "Sociales", 3.5)
;

-- Actualizar los datos
UPDATE estudiantes
SET edad = 21
WHERE id_estudiante = 2;

-- Eliminar
DELETE FROM notas
WHERE id_estudiante = 3;

DELETE FROM estudiantes
WHERE id_estudiante = 3;

-- comandos DQL 
-- obtener todos los estudiantes

SELECT * FROM estudiantes;

-- condiciones con WHERE
SELECT * FROM estudiantes WHERE edad > 18;

-- consulta INERT JOIN
SELECT estudiantes.nombre, estudiantes.apellido, notas.aignatura, notas.calificacion
FROM estudiantes
INNER JOIN notas ON estudiantes.id_estudiante = notas.id_estudiante;
```
