---
title: "Introduction"
teaching: 10
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions

- How can I run an HPC workflow in a reproducible way?
- What is the easiest way to create a scaling experiment for an HPC application?
- How do I identify the optimal runtime configuration for an application
  on an HPC system?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Enumerate the benefits of workflow automation.
- Describe potential use cases for HPC workflow automation using JUBE.

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

The primary goal of this session is to present potential use cases for JUBE and enable participants to apply these insights to their own workflows on HPC systems.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

When applying for computing time on HPC systems, applicants are often required to provide measurements on different scales of parallelism.
Furthermore, preparing performance measurements often involves an application-specific workflow as well as platform-specific configurations.
The objective of this lesson is to enable users of HPC systems to run performance measurements with minimal intervention with high reproducibility, using the [Jülich Benchmarking Environment (JUBE)](https://apps.fz-juelich.de/jsc/jube/docu/index.html) [1].

It is important to understand that, although JUBE emerged as a benchmarking system, it actually is a workflow management system, where application and system benchmarking is one of its potential uses.
Further use cases may include running multiple HPC workflows as integration tests during application development and defining reproducible execution workflows for data generation for publications.

::: instructor
It is important for the learners to understand that JUBE itself **does know what
makes your workflow reproducible on its own**.
To create a reproducible workflow learners will have to **identify which
information and actions make the specific workflow reproducible**, and use JUBE
to **automatically collect and execute** those, respectively.
:::

::: caution

### Reproducibility Note
JUBE is an automation tool. This means that it **does not** intrinsically make
your workflows reproducible; rather, it **enables you to automate** all the actions that
could make your workflow reproducible.

:::

The key benefits of using JUBE are:

- It enables systematic and reproducible benchmarks.
- It provides a flexible, script-based framework to set up tasks and control
  various aspects of the execution.
- It allows for custom workflows that can adapt to different HPC platforms.
- It provides a powerful tagging system to influence execution of a given
  workflow.
- It automatically isolates your workflow steps so concurrent tasks don't
  overwrite or re-use files in unintentionally shared execution environments.
- It enables efficient parameter space exploration.
- It allows to easily retrieve strings from runtime output and create tables
  and CSV files.

::::::::::::::::::::::::::::::::::::: discussion

Consider your own workflows on an HPC system.
What individual steps are involved?
Please discuss this in groups.

:::::::::::::::::::::::::::::::::::::::::::
:::::::::::::::::::::::: hint

### List of potential discussion points
Steps may include:

- Loading and preparing the software environment
- Building a software package
- Creating a runtime configuration for your application
- Creating a scheduler job script
- Submitting a job to the scheduler
- Extracting strings from application output.

:::::::::::::::::::::::::::::::::

[JUBE](https://www.fz-juelich.de/jsc/jube/) is written and maintained by the [Jülich Supercomputing
Centre](https://www.fz-juelich.de/jsc/) at [Forschungszentrum
Jülich](https://www.fz-juelich.de/) in Germany.
It is written in Python 3. Please use a Python 3 interpreter when working with it.
The user can write configurations in XML or YAML syntax.
It is freely [available for download](https://www.fz-juelich.de/en/ias/jsc/services/user-support/software-tools/jube/download) and also available via HPC software package managers, such as [Spack](https://spack.io/) and [EasyBuild](https://easybuild.io/).


::: challenge

Create an empty workspace for all subsequent challenges in this lesson.


::: solution

It is best to start with an empty directory. You are free to choose any name,
but for the sake of this lesson, we will use `jube-workspace/`.

```sh
$ mkdir jube-workspace/
$ cd jube-workspace/
$ pwd
```

```output
/home/user/jube-workspace
```
:::
:::


::::::::::::::::::::::::::::::::::::: keypoints

- Workflow automation aids in getting reproducible results.
- JUBE enables execution and management of complex workflows on HPC systems.
- JUBE simplifies exploration of a large parameter space of measurements.
- JUBE automatically isolates the individual workpackages of a run in separate directories steps to avoid
  individual concurrent workpackages to overwrite or unintentional reuse of intermediate
  data.
- JUBE does not inherently generate fully reproducible workflows, but users can manually record any settings that make the workflow reproducible.


::::::::::::::::::::::::::::::::::::::::::::::::



