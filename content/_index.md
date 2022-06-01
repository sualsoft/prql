---
####################### Genaral #########################
layout: home
title: PRQL

####################### Hero section #########################
hero_section:
  enable: true
  tagline: " <span>P</span>ipelined <span>R</span>elational <span>Q</span>uery <span>L</span>anguage, pronounced <span>“Prequel”</span>. "
  heading: "PRQL is a modern language for transforming data"
  bottom_text: "a simpler and more powerful SQL."
  button:
    enable: true
    link: "https://prql-lang.org/reference/"
    label: "Reference"

####################### Principles section #########################
principle_section:
  enable: true
  title: "Principles"
  tagline: "PRQL is a modern language for transforming data — a simpler and more powerful SQL. Like SQL, it’s readable, explicit and declarative. Unlike SQL, it forms a logical pipeline of transformations, and supports abstractions such as variables and functions. It can be used with any database that uses SQL, since it transpiles to SQL."
  items:
    - icon: "bx bx-dots-vertical"
      title: "Pipelined"
      main_text: "PRQL is a linear pipeline of transformations"
      content: "— each line of the query is a transformation of the previous line’s result. This makes it easy to read, and simple to write."

    - icon: "bx bx-code-alt"
      title: "Simple"
      main_text: "PRQL serves both sophisticated engineers and analysts without coding experience."
      content: "By providing simple, clean abstractions, the language can be both powerful and easy to use."

    - icon: "bx bx-book-open"
      title: "Open"
      main_text: "PRQL will always be open-source"
      content: "free-as-in-free, and doesn’t prioritize one database over others. By compiling to SQL, PRQL is instantly compatible with most databases, and existing tools or programming languages that manage SQL. Where possible, PRQL unifies syntax across databases."

    - icon: "bx bx-extension"
      title: "Extensible"
      main_text: "PRQL can be extended through its abstractions"
      content: "and its explicit versioning allows changes without breaking backward-compatibility. PRQL allows embedding SQL through S-Strings, where PRQL doesn’t yet have an implementation."

    - icon: "bx bx-line-chart"
      title: "Analytical"
      main_text: "PRQL’s focus is analytical queries"
      content: "we de-emphasize other SQL features such as inserting data or transactions."

####################### SQL Section #########################
sql_section:
  enable: true
  title: "Motivation"
  subtitile: "PRQL’s SQL queries"
  content: "Even though wildly adopted and readable as a sentence, SQL is inconsistent and becomes unmanageable as soon as query complexity goes beyond the most simple queries. <br><br> Click the link to show how PRQL can simplifies analytical SQL queries."
  main_icon: "bx bx-trip"
  button:
    enable: true
    link: "/motivation/"
    label: "Here are examples"

####################### Tools Section #########################
tools_section:
  enable: true
  title: "TOOLS"
  main_icon: "bx bx-code-block"
  right_sections:
    - link: "https://github.com/prql/prql"
      label: "prql-compiler"
      text: " reference compiler implementation"

    - link: https://github.com/prql/PyPrql
      label: "PyPrql"
      text: "python TUI for connecting to databases. Has some great features, including a native interactive console with auto-complete for column names,"

    - link: "https://pypi.org/project/pyprql/"
      label: "prql-py"
      text: "Python compiler library,"

    - link: "https://www.npmjs.com/package/prql-js"
      label: "prql-js"
      text: "JavaScript compiler library."

####################### Intergrations Section #########################
integrations_section:
  - title: "Use a plugin for your existing tool"
    list_1:
      link: "/"
      label: "dbt-prql"
      text: ": TODO"
    list_2:
      link: "/"
      label: "jupyter"
      text: ": TODO"

  - title: "Install the compiler"
    list_1: "Install with cargo: <span>cargo install prql</span>"
    list_2: "Install with pip: <span>cargo pip install pyprql</span>"

####################### Call to action section #########################
call_to_action:
  enable: true
  title: "Keep in touch"
  text: "Star this repo and Send a link to PRQL to a couple of people whose opinion you respect."
  button:
    - link: "https://discord.com/invite/eQcfaCmsNc"
      label: "Join the Discord"
      enable: true

    - link: "https://github.com/prql/prql"
      label: "Contribute to PRQL"
      enable: true
---

## my name

```prql
from employees                                # Each line transforms the previous result.
filter start_date > @2021-01-01               # Clear date syntax.
derive [                                      # `derive` adds columns / variables.
  gross_salary = salary + payroll_tax,
  gross_cost = gross_salary + benefits_cost   # Variables can use other variables.
]
filter gross_cost > 0
group [title, country] (                      # `group` runs a pipeline over each group.
  aggregate [                                 # `aggregate` reduces each group to a row.
    average salary,
    sum     salary,
    average gross_salary,
    sum     gross_salary,
    average gross_cost,
    sum_gross_cost = sum gross_cost,          # `=` sets a column name.
    ct = count,
  ]
)
sort [sum_gross_cost, -country]               # `-country` means descending order.
filter ct > 200
take 20
```
