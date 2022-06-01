---
title: Roadmap
layout: roadmap

hero_area:
  enable: true
  title: Roadmap
  content:
    - I’m excited and inspired by the level of enthusiasm behind the project, both from individual contributors and the broader community of users who are unsatisfied with SQL. We currently have an initial working version for the intrepid early user.
    - I’m hoping we can build a beautiful language, an app that’s approachable & powerful, and a vibrant community. Many projects have reached the current stage and fallen, so this requires compounding on what we’ve done so far.

######################### Service #####################
roadmap:
  enable: true
  roadmap_item:
    # roadmap item loop
    - title: "Language design"
      icon: "bx bx-message-rounded-dots"
      content: "Already since becoming public, the language has improved dramatically, thanks to the feedback of dozens of contributors. The current state of the basics is now stable and while we’ll hit corner-cases, I expect we’ll only make small changes to the existing features — even as we continue adding features.  <br><br> Feel free to post questions or continue discussions on Language Design Issues."
      button:
        enable: true
        label: "Language Design Issues"
        link: "https://github.com/prql/prql/issues?q=is%3Aissue+is%3Aopen+label%3Alanguage-design"

    # roadmap item loop
    - title: "Documentation"
      icon: "bx bx-help-circle"
      content: Currently the language documentation is at <a href='https://prql-lang.org/reference'> https://prql-lang.org/reference<sup><i class="bx bx-link-external"></i></sup></a>. <br><br> If you’re up for contributing and don’t have a preference for writing code or not, this is the area that would most benefit from your contribution. Issues are tagged with documentation.
      button:
        enable: true
        label: "Documentation"
        link: "https://github.com/prql/prql/labels/documentation"

    # roadmap item loop
    - title: "Friendliness"
      icon: "bx bxs-dog"
      content: "Currently the language implementation is not sufficiently friendly, despite significant recent improvements. We’d like to make error messages better, sand off sharp corners, etc.<br><br> Both bug reports of unfriendliness, and code contributions to improve them are welcome; there’s a friendliness label."
      button:
        enable: true
        label: "Friendliness"
        link: "https://github.com/prql/prql/issues?q=is%3Aissue+label%3Afriendlienss+is%3Aopen"

    # roadmap item loop
    - title: "Fast feedback"
      icon: "bx bx-star"
      content: "As well as a command-line tool that transpiles queries, we’d like to make developing in PRQL a wonderful experience, where it feels like it’s on your side:"
      ul:
        - Syntax highlighting in more editors; currently we have a basic <a href='https://github.com/prql/prql-code'>VSCode extension<sup><i class="bx bx-link-external"></i></sup></a>.

        - Initial type-inference, where it’s possible without connecting to the DB, e.g.<a href='https://github.com/prql/prql/pull/55'>#55<sup><i class="bx bx-link-external"></i></sup></a>.

        - Improvements or integrations to the  <a href='https://prql-lang.org/playground/s'>live in-browser compiler<sup><i class="bx bx-link-external"></i></sup></a>, including querying actual tables.
        - (I’m sure there’s more, ideas welcome)

      button:
        enable: true
        label: "Live in-browser compiler"
        link: "https://prql-lang.org/playground/"

    # roadmap item loop
    - title: "Integrations"
      icon: "bx bx-intersect"
      content: "PRQL is focused at the language layer, which means we can easily integrate with existing tools & apps. This will be the primary way that people can start using PRQL day-to-day. Probably the most impactful initial integrations will be tools that engineers use to build data pipelines, like dbt-prql."
      button:
        enable: true
        label: "Dbt-prql"
        link: "https://github.com/prql/prql/issues/375"

    # roadmap item loop
    - title: "Database cohesion"
      icon: "bx bxs-data"
      content: "One benefit of PRQL over SQL is that auto-complete, type-inference, and error checking can be much more powerful. <br><br> We’d like to build this out. It’s more difficult to build, since it requires a connection to the database in order to understand the schema of the table."
      button:
        enable: false
        label: "Dbt-prql"
        link: "https://github.com/prql/prql/issues/375"

    # roadmap item loop
    - title: "Not in focus"
      icon: "bx bx-crosshair"
      content: "We should focus on solving a distinct problem really well. PRQL’s goal is to make reading and writing analytical queries easier, and so for the moment that means putting some things out of scope:"
      ul:
        - Building infrastructure outside of queries, like lineage. dbt is excellent at that!  <a href='https://github.com/prql/prql/issues/13'>#13<sup><i class="bx bx-link-external"></i></sup></a>.

        - Writing DDL / index / schema manipulation / inserting data <a href='https://github.com/prql/prql/issues/16'>(#16)<sup><i class="bx bx-link-external"></i></sup>.</a>
      button:
        enable: false
        label: "Dbt-prql"
        link: "https://github.com/prql/prql/issues/375"
---
