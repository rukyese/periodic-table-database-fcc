# Periodic Table Database

This repository contains a Bash script and a PostgreSQL database for managing information about chemical elements in the periodic table. The project includes a database that stores details about each element, such as its atomic number, name, symbol, atomic mass, melting point, and boiling point. The Bash script allows users to query the database and retrieve information about elements based on their atomic number, symbol, or name.

## Files

- periodic_table.sql: SQL dump of the periodic_table database schema and sample data.
- element.sh: Shell script that interacts with the PostgreSQL database to retrieve information about an element by atomic number, symbol, or name.

## How to Use

### Clone the Repository

```bash
git clone https://github.com/rukyese/periodic-table-database-fcc.git
cd periodic-table-database-fcc
```

### Rebuild the Database

You can rebuild the database by entering the following command in a terminal where the periodic_table.sql file is located:

```bash
psql -U postgres < periodic_table.sql
```

This will create the periodic_table database and load the relevant data.

### Run the element.sh Script

The element.sh script allows you to query elements from the database. To use it:

1. First, ensure that the script has executable permissions:

```bash
chmod +x element.sh
```

2. Run the script with an argument (atomic number, symbol, or name of an element). For example:

```bash
./element.sh 1
```

Output:

```text
The element with atomic number 1 is Hydrogen (H). It's a nonmetal, with a mass of 1.008 amu. Hydrogen has a melting point of -259.1 celsius and a boiling point of -252.9 celsius.
```

You can also query by symbol or name:

```bash
./element.sh H
```

```bash
./element.sh Hydrogen
```

Both will provide the same information for Hydrogen.

3. If the input doesn't match any element, the script will output:

```text
I could not find that element in the database.
```
