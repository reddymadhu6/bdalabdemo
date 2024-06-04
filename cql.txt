CREATE KEYSPACE IF NOT EXISTS Company WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};

USE Company;

CREATE TABLE IF NOT EXISTS Employee (
    id INT PRIMARY KEY,
    name TEXT,
    department TEXT,
    designation TEXT,
    salary FLOAT
);
INSERT INTO Employee (id, name, department, designation, salary) VALUES (1, 'John Doe', 'IT', 'Manager', 90000);
INSERT INTO Employee (id, name, department, designation, salary) VALUES (2, 'Jane Smith', 'HR', 'Manager', 95000);
INSERT INTO Employee (id, name, department, designation, salary) VALUES (3, 'Alice Johnson', 'Finance', 'Assistant Manager', 75000);
INSERT INTO Employee (id, name, department, designation, salary) VALUES (4, 'Bob Williams', 'IT', 'Manager', 100000);
SELECT name, department FROM Employee WHERE designation = 'Manager' AND salary > 85000 ORDER BY salary DESC;
UPDATE Employee SET previous_experience = 15 WHERE id = 4;

COPY Employee (id, name, department, designation, salary) FROM 'file_path.csv' WITH HEADER = true;
