# Spot Check 3

Let's implement this **M : N** table inside of `/solutions/check_3.sql`:

  

-   Create a `student` table with the fields
    -   `s_id` - int, PK
    -   `s_name` - string
    -   `is_brilliant` - bool
-   Create a `teacher` table with the fields
    -   `t_id` - int, PK
    -   `t_name` - string
    -   `is_tenured` - bool
-   Create the `student_teacher` table we talked about before
    -   `student_id` - int, FK
    -   `teacher_id` - int, FK

  

To save you some grunt work, here's some student and teacher data:

```sql
INSERT INTO Student VALUES (1, 'Ryan', true); -- note the use of true for TRUE
INSERT INTO Student VALUES (2, 'Leo', true); 
INSERT INTO Student VALUES (3, 'Ernie', false); -- and false for FALSE in PostgreSQL

INSERT INTO Teacher VALUES (1, 'Levine', true);
INSERT INTO Teacher VALUES (2, 'Foster', false);
INSERT INTO Teacher VALUES (3, 'Schwimmer', false);
```
  

But you'll have to insert all rows in the `student_teacher` table yourself using the breakdown below:

  

**Ryan's** teachers: Levine, Foster
**Leo's** teachers: all three
**Ernie's** teachers: Levine (Ernie is a slacker)

  

**Note:** Once we've entered the Ryan-Levine relationship, there is **no need** to enter Levine-Ryan - they're the same in the join table!

  

When you `SELECT * FROM student_teacher` you should see the following:

  

![](https://s3-us-west-2.amazonaws.com/learn-app/lesson-images/sqlManyToManyTable.PNG)

  

**<span style="color: red">Note for the test:</span>**  the system is only checking the table creation, so **only** add the `CREATE`... code to the `check_3.sql` file. **i.e. Remove all the `INSERT` code**

  

See [this codepen](https://codepen.io/ElevationPen/pen/rgzzWm?editors=0010) for a solution.
