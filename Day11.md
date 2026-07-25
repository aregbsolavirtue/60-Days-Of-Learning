# Day 11 – Spring Data JPA

## Overview
Spring Data JPA is a Spring module that simplifies database operations. It allows developers to perform CRUD (Create, Read, Update, Delete) operations without writing most SQL queries manually.

It builds on:
- JPA (Java Persistence API) – a specification
- Hibernate – the most popular implementation of JPA

---

## What is JPA?

JPA (Java Persistence API) is a specification that defines how Java objects are stored and retrieved from relational databases.

**Important:**
- JPA is NOT a framework.
- JPA is a set of rules.
- Hibernate is a framework that implements those rules.

Relationship:

JPA (Specification)
        ↓
Hibernate (Implementation)
        ↓
Spring Data JPA (Simplifies Hibernate)

---

## Benefits of Spring Data JPA

- Reduces boilerplate code
- Automatically generates SQL for common operations
- Easy CRUD operations
- Supports pagination and sorting
- Easy integration with Spring Boot
- Better code readability and maintenance

---

## Entity

An Entity is a Java class that represents a table in the database.

Example:

```java
@Entity
public class Student {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;

    private int age;
}
```

This class maps to a database table called Student.

---

## Common JPA Annotations

### @Entity
Marks a class as a database entity.

```java
@Entity
```

---

### @Id

Defines the primary key.

```java
@Id
private Long id;
```

---

### @GeneratedValue

Automatically generates primary key values.

```java
@GeneratedValue(strategy = GenerationType.IDENTITY)
```

---

### @Table

Specifies the database table name.

```java
@Table(name="students")
```

---

### @Column

Customizes a database column.

```java
@Column(name="student_name")
```

---

### @Transient

Excludes a field from being stored in the database.

---

## Repository

Repositories handle communication between the application and the database.

Example:

```java
public interface StudentRepository
extends JpaRepository<Student, Long> {

}
```

JpaRepository provides built-in methods.

---

## Common JpaRepository Methods

Save an object

```java
save(student);
```

Retrieve all records

```java
findAll();
```

Find by ID

```java
findById(id);
```

Delete by ID

```java
deleteById(id);
```

Count records

```java
count();
```

Check if data exists

```java
existsById(id);
```

---

## CRUD Operations

CRUD stands for:

- Create → save()
- Read → findAll(), findById()
- Update → save()
- Delete → deleteById()

---

## Custom Query Methods

Spring Data JPA can generate queries from method names.

Example:

```java
List<Student> findByName(String name);
```

Spring automatically generates:

```sql
SELECT * FROM student WHERE name = ?
```

Another example:

```java
List<Student> findByAge(int age);
```

No SQL is required.

---

## Architecture Flow

Client

↓

Controller

↓

Service

↓

Repository

↓

Database

---

## Spring Data JPA vs JDBC

| JDBC | Spring Data JPA |
|------|-----------------|
| Manual SQL | Automatic SQL generation |
| More coding | Less coding |
| Manual mapping | Automatic mapping |
| Harder to maintain | Easier to maintain |

---

## Advantages

- Faster development
- Less SQL writing
- Cleaner code
- Easy maintenance
- Built-in CRUD methods
- Supports pagination and sorting

---

## Key Exam Points

- JPA is a specification.
- Hibernate implements JPA.
- Spring Data JPA simplifies Hibernate.
- An Entity represents a database table.
- A Repository handles database operations.
- JpaRepository provides ready-made CRUD methods.
- CRUD means Create, Read, Update, Delete.

---

## Summary

Spring Data JPA makes database programming much easier in Spring Boot. Instead of writing SQL for every operation, developers work with Java objects, while Spring automatically handles most database interactions. This results in cleaner, faster, and more maintainable applications.