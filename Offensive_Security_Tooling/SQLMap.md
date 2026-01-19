## SQLMap Overview

SQLMap is an open source, automated tool used to **detect and exploit SQL injection vulnerabilities** in web applications.
It simplifies the process of identifying vulnerable parameters and extracting database information.

SQLMap is commonly preinstalled on security focused Linux distributions such as Kali Linux. If it is not installed, it can be added easily.

SQLMap is a **command line tool**, so it is used entirely from the terminal.

---

## Getting Help in SQLMap

```
sqlmap --help
```

This command displays all available options and flags.

### Wizard Mode

```
sqlmap --wizard
```

The wizard mode guides the user step by step by asking questions.
This is ideal for beginners who are not yet familiar with all the flags.

---

## Database Enumeration Flags

Once SQLMap detects an injectable parameter, it can extract database information.

### List All Databases

```
--dbs
```

This flag retrieves all database names available on the target.

---

### List Tables in a Database

```
-D database_name --tables
```

- `-D` specifies the database name
- `--tables` lists all tables inside that database

---

### Dump Table Data

```
-D database_name -T table_name --dump
```

- `-T` specifies the table name
- `--dump` extracts all records from the table

These flags allow deep enumeration of database contents.

---

## GET Based SQL Injection Testing

If a web application uses **GET parameters** in the URL, SQLMap can test them directly.

Example URL structure:

```
http://example.com/search?cat=1
```

- `cat` is the parameter
- `1` is the value

### Testing with SQLMap

```
sqlmap -u "http://example.com/search?cat=1"
```

This method is used when data is passed through the URL.

---

## POST Based SQL Injection Testing

Some applications send data through the **request body**, not the URL.
Common examples include:

- Login forms
- Registration forms
- Contact forms

To test these, you must capture the POST request.

---

## Testing an Intercepted POST Request

1. Intercept the request using a proxy tool like Burp Suite
2. Save the request to a text file

### Run SQLMap with the Request File

```
sqlmap -r intercepted_request.txt
```

- `-r` tells SQLMap to read the raw HTTP request from a file
- SQLMap automatically identifies parameters inside the request

This method is essential for testing authentication forms and hidden parameters.

---

## Key Points to Remember

- SQLMap automates SQL injection detection and exploitation
- `--wizard` is beginner friendly
- `--dbs`, `--tables`, and `--dump` are used for database enumeration
- `-u` is used for GET based testing
- `-r` is used for POST based testing with intercepted requests
