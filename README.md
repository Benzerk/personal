## Markdown

- [Markdown and Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown)

## Git

- [Git Documentation](https://git-scm.com/docs)
- [Git Ebook](https://git-scm.com/book/en/v2)
- [Git Notes for Profesionals](https://books.goalkicker.com/GitBook/)

### Useful Commands

```bash
# Local Configuration
git config --global user.name ${username}
git config --global user.email ${email}

# Create Branch from Scratch
git checkout --orphan temp
```

## SQL

- [SQL Notes for Profesionals](https://books.goalkicker.com/SQLBook/)

### Useful Queries

```SQL
-- Differences between tables
(   SELECT * FROM table1
    EXCEPT
    SELECT * FROM table2)  
UNION ALL
(   SELECT * FROM table2
    EXCEPT
    SELECT * FROM table1)
```

```SQL
-- Recursive CTE
WITH hierarchy AS (
    SELECT     
        e.id AS employee_id,
        e.first_name,
        e.last_name,
        e.boss_id,
        0 AS hierarchy_level
    FROM employees AS e
    WHERE e.manager_id IS NULL
UNION ALL
    SELECT   
        e.id AS employee_id,
        e.first_name,
        e.last_name,
        e.boss_id,
        h.hierarchy_level + 1 AS hierarchy_level
    FROM employees AS e
        JOIN hierarchy AS h ON e.id = h.employee_id
)
SELECT * FROM hierarchy
```
