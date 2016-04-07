---
layout: lesson
root: .
title: Joins and aliases
minutes: 30
---


Joins
-----

To combine data from two tables we use the SQL `JOIN` command, which comes after
the `FROM` command.

We also need to tell the computer which columns provide the link between the two
tables using the word `ON`.  What we want is to join the data with the same
row id codes.

    SELECT *
    FROM Demographics
    JOIN MeasuresofBirthAndDeath
    ON Demographics.rowid = MeasuresofBirthAndDeath.rowid;


`ON` is like `WHERE`, it filters things out according to a test condition.  We use
the `table.colname` format to tell the manager what column in which table we are
referring to.

We often won't want all of the fields from both tables, so anywhere we would
have used a field name in a non-join query, we can use `table.colname`.

For example, what if we wanted to compare the poverty rate with the infant mortality rate?

    SELECT Demographics.County, Demographics.Poverty, MeasuresOfBirthAndDeath.Infant_Mortality
    FROM Demographics 
    JOIN MeasuresofBirthandDeath
    ON Demographics.rowid = MeasuresofBirthAndDeath.rowid;
    
> ### Challenge:
>
> Write a query that returns the County name, state abbreviation, population density, and total deaths of every county

Joins can be combined with sorting, filtering, and aggregation.  So, if we
wanted average poverty rate and infant mortality rate for each state we use the following.

    SELECT Demographics.State, AVG(Demographics.Poverty), AVG(MeasuresofBirthandDeath.Infant_Mortality)
    FROM Demographics JOIN MeasuresofBirthandDeath
    ON Demographics.rowid = MeasuresofBirthandDeath.rowid
    GROUP BY Demographics.State;

> ### Challenge:
>
> Write a query that returns a list of the states in order of their average infant mortality rate.

> ### Challenge:
>
>
> Write a query that returns the name of each state with the total deaths of each state.


Aliases
-------

As queries get more complex names can get long and unwieldy. To help make things
clearer we can use aliases to assign new names to things in the query.

We can alias both table names:

    SELECT D.County, D.Poverty, M.Infant_Mortality, M.Total_Births
    FROM Demographics AS D JOIN MeasuresOfBirthandDeath AS M
    ON D.rowid = M.rowid;

And column names:

    SELECT D.CHSI_County_Name AS co, D.Poverty AS po, M.Infant_Mortality AS im, M.Total_Births AS bi
    FROM Demographics AS D JOIN MeasuresOfBirthandDeath AS M
    ON D.rowid = M.rowid;

The `AS` isn't technically required, so you could do

    SELECT D.County co
    FROM Demographics D

but using `AS` is much clearer so it is considered good style to use it.

    [join by County]
    
There is a better way to `JOIN` datasets like this one rather than trusting that they are presorted by the implicitly defined primary key, rowid. It is possible to `JOIN` using multiple columns if that is what is necessary to create a unique identifier for each record.

    SELECT Demographics.County, Demographics.Poverty, MeasuresOfBirthAndDeath.Infant_Mortality
    FROM Demographics
    JOIN MeasuresofBirthAndDeath
    ON (Demographics.State = MeasuresofBirthAndDeath.CHSI_State_Name) 
    AND (Demographics.County = MeasuresofBirthAndDeath.CHSI_County_Name)



> ### Challenge (optional):
>


Previous: [SQL Aggregation](02-sql-aggregation.html) Next: [Wrapup: Importing to Python and Plotting](04-sqlite-and-python.md)
