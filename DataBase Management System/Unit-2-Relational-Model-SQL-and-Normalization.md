# 📘 DBMS - Unit 2: Relational Model, SQL & Normalization

> Source: Handwritten Notes (Structured)  
> Reference: Original notes :contentReference[oaicite:1]{index=1}

---

# 🔹 1. Relational Algebra

## 📌 Definition
- Procedural query language  
- Specifies **how to get data**

---

## 🔸 Basic Operations

| Operation   | Symbol | Description |
|------------|--------|------------|
| Select     | σ      | Row filtering |
| Project    | π      | Column filtering |
| Union      | ∪      | Combine results |
| Set Difference | − | Records in one not in another |
| Cartesian Product | × | Combine all rows |

---

## 🔸 Important Operations

### 1. Select (σ)
- Filters rows  
- Example:σ branch = 'CSE' (Student)
- 
---

### 2. Project (π)
- Selects columns  
- Example: π Name, RollNo (Student)

 
---

### 3. Rename (ρ)
- Rename table or attributes
- ρ NewName (OldTable)

- 
---

# 🔹 2. SQL (Structured Query Language)

## 📌 SELECT Statement

### Syntax:
```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```
###Example:
SELECT EmpName
FROM Employee
WHERE Salary > 50000;


# Explanation

**SELECT** → columns choose karna  
**FROM** → table choose karna  
**WHERE** → condition lagana

## 3. Aggregate Functions
| Function | Description |
| --- | --- |
| COUNT() | Total rows |
| SUM() | Sum of values |
| AVG() | Average |
| MIN() | Minimum |
| MAX() | Maximum |

**Example:**
```sql
SELECT AVG(Marks)
FROM Student;
```

## 4. Normalization & Anomalies
### Normalization
- Process of organizing data  
- Removes redundancy  
- Improves consistency

### ❌ Anomalies
1. **Update Anomaly:**
   - Same data multiple places → inconsistency  
2. **Insertion Anomaly:**
   - Data insert nahi kar paate due to dependency  
3. **Deletion Anomaly:**
   - Important data accidentally delete ho jata

## 5. Functional Dependency (FD)
### Definition
- One attribute determines another  
- X → Y  
- X = Determinant, Y = Dependent

### Example:
- RollNo → Name

## 6. Armstrong’s Axioms
1. **Reflexivity:**
   - If Y ⊆ X → X → Y  
2. **Augmentation:**
   - If X → Y → XZ → YZ  
3. **Transitivity:**
   - If X → Y and Y → Z → X → Z

## 7. Normal Forms
✅ **1NF (First Normal Form):**
- Only atomic values  
- No multivalued attributes  
✅ **2NF (Second Normal Form):**
- No partial dependency  
depends on full primary key  
✅ **3NF (Third Normal Form):**
- No transitive dependency  
does not depend on non-key attributes directly, only through primary key.
✅ **BCNF (Boyce-Codd Normal Form):**
every determinant must be a candidate key.

## 8. SQL Joins
### Definition:
purpose: Combine data from multiple tables.
### Types of Joins:
ospecifics:
define each with syntax and behavior.
details:
summarize with examples.
description:
types include INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN.
each explained with their behavior regarding matching and unmatched rows.
'tips': example queries for INNER JOIN provided.
note: NULL for unmatched right table in LEFT JOIN, etc.
details for FULL OUTER JOIN included.
bullet points for clarity.
definitions and examples formatted properly.
display code snippets in markdown code blocks where applicable.
documentation style formatting applied throughout.
bullet points used to organize information clearly.
