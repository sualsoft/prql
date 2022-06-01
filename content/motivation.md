---
title: Motivation
layout: motivation

hero_area:
  enable: true
  title: Motivation
  sub_title: A simple example
  text:

abstraction_section:
  enable: true
  title: "lack of abstractions"
  subtitle: "Even this simple query demonstrates some of the problems with SQL’s lack of abstractions:"
  items:
    - icon: "bx bxs-doughnut-chart"
      title: "Unnecessary repetition"
      content: "the calculations for each measure are repeated, despite deriving from a previous measure. The repetition in the WHERE clause obfuscates the meaning of the expression."

    - icon: "bx bx-cog"
      title: "Operators have multiple functions"
      content: "the SELECT operator both creates new aggregations, and selects which columns to include."

    - icon: "bx bx-math"
      title: "Functions have multiple operators"
      content: "HAVING & WHERE are fundamentally similar operations applied at different stages of the pipeline, but SQL’s lack of pipeline-based precedence requires it to have two different operators."

    - icon: "bx bx-code-curly"
      title: "Awkward syntax"
      content: "when developing the query, commenting out the final line of the SELECT list causes a syntax error because of how commas are handled, and we need to repeat the columns in the GROUP BY clause in the SELECT list."

simple_sql:
  enable: true
  title: "Here’s a fairly simple SQL query:"
  content:
    - As well as using variables to reduce unnecessary repetition, the query is also more readable — it flows from top to bottom, each line representing a transformation of the previous line’s result. For example, TOP 20 / take 20 modify the final result in both queries — but only PRQL represents it as the final transformation. And context is localized — the aggregate transform is immediately wrapped in a group transform containing the columns to group by.

    - While PRQL is designed for reading & writing by people, it’s also much simpler for code to construct or edit PRQL queries. In SQL, adding a filter to a query involves parsing the query to find and then modify the WHERE statement, or wrapping the existing query in a CTE. In PRQL, adding a filter just involves appending a filter transformation to the query.

complex_example:
  enable: true
  title: "A more complex example"
  sub_title: "The implemented version of PRQL supports some but not all these features."
  botton_text: "Here’s another SQL query, which calculates returns from prices on days with valid prices."
  content: " This might seem like a convoluted example, but it’s taken from a real query. Indeed, it’s also simpler and smaller than the full  logic — note that it starts from price_adjusted, whose logic had to be split into a previous query to avoid the SQL becoming even less readable."

same_query:
  enable: true
  title: "Here’s the same query with PRQL:"
  left_paragraph:
    - Because we define the functions once rather than copying & pasting thecode, we get all the benefits of encapsulation and extensibility —  we have reliable & tested functions, whose purpose is explicit, which we can share across queries and between colleagues.
    - We needed a CTE in the SQL query, because the lack of variables would have required a nested window clause, which isn’t allowed. With PRQL, our logic isn’t constrained by these arbitrary constraints — and is more compressed as a result.

  right_paragraph:
    - "The larger query demonstrates PRQL orthogonality. PRQL has fewer keywords than SQL, and each of them does something specific and composable; for example:"

  right_list:
    - "group maps a pipeline over groups; whether in a table context — GROUP BY in SQL — or within a window — PARTITION BY in SQL."

    - "A transform in context of a group does the same transformation to the group as it would to the table — for example finding the rolling sum of a column. For more on this equivalence, check out group’s documentation"

    - "filter filters out rows which don’t meet a condition. That can be before an aggregate — WHERE in SQL — after an aggregate — HAVING in SQL — or within a window — QUALIFY in SQL."
---
