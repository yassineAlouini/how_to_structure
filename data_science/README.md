Introduction
------------

Structuring a data science project is often a practice that is neglacted
(or even absent). <br><br>In fact, most people will through their entire
code in a single file. This is fine if you are doing exploratory
analysis or hacking for a weekend project. However, this same practice
becomes a hurdle if you are working on complex projects with multiple
cleaning, feature enginerring, modeling and testing steps.

 Basic principles
-----------------

1.  Store all the inputs and outputs of your project.
2.  Add a timestamp to the produced results. For example, if you train a
    model and need to save it for later use, name it as:
    `<date>_<model>.<file_format>`
3.  Elaborating on the previous step, add a meta-data file containing a
    description about each file and what it contains (keep the
    description short and to the point)
4.  Separate your project into these different folders:
    -   **data**: where to store the raw and transformed data
    -   **features**: where to put features creation and extraction
        scripts
    -   **models**: where you put different machine learning models
    -   **evaluation**: where put the evaluation scripts
    -   **output**: where to store different outputs (graphs, models...)
    -   **main**: where you connect the different modules of your
        project. It is the entry point for your project.

5.  In addition to the ones listed in the previous step, you can also
    add an **utils** folder where to put reusable functions and modules
    and a **documentation** one.

6.  Avoid commiting large data sets and graphs. Instead, store data
    somewhere else (cloud-based storage for example) and include the
    scripts that generates the graphs (with decent amount of
    documentation).

7.  Add as many README.md files as there are folders.

8.  Provide examples for each step of your data science pipeline.

A project structure
-------------------

Here is a structure for a mildly complex data science project:

    .
    +-- data
    |   +-- raw
    |   +-- transformed
    +-- features
    |   +-- creation
    |   |  +-- feature_1
    |   |  +-- feature_2
    |   +-- selection
    +-- models
    |   +-- splitting
    |   +-- model_1
    |   +-- model_2
    |   ...
    +-- evaluation
    |
    +-- utils
    |   +-- metrics
    |   +-- graph_generators
    |   ...
    +-- documentation
    +-- output
    |   +-- graphs
    |   +-- models
    +-- main

*Note*: This is a fairly generic structure that can be customized and
optimized for different uses. I will provide concrete examples in the
next `examples` folder.
