# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 5: Disaster Relief + Classification

### Overview

You've learned about accessing and using remote databases, and more advanced topics for conducting classifications. Now, let's put these skills to the test!

You're working as a data scientist with a research firm that specializes in emergency management. In advance of client work, you've been asked to create and train a logistic regression model that can show off the firm's capabilities in disaster analysis.

Frequently after a disaster, researchers and firms will come in to give an independent review of an incident. While your firm doesn't have any current client data that it can share with you so that you may test and deploy your model, it does have data from the 1912 titanic disaster that it has stored in a remote database.

In this project, we'll be using data on passengers from the Titanic disaster to show off your analytical capabilities. The data is stored in a remote database, so you'll need to set up a connection and query the database (using Python!). After, you'll construct a logistic regression model and test/validate its results so that it will be ready to deploy with a client.  Then you'll move on to using other clasification models.

**Goal:** Your job is to perform the following tasks:

- Collect your data from an AWS PostgreSQL instance via Python + Jupyter Notebook
- Perform any necessary data wrangling in advance of building your model
- Create a logistic regression model to figure out the likelihood of a passenger's survival
- Gridsearch optimal parameters for the logistic regression model
- Create a kNN model and optimize its parameters with gridsearch
- Create a decision tree classifier and optimize its parameters with gridsearch
- Examine and explain the confusion matrices and ROC curves
- Create a report of your findings and detail the accuracy and assumptions of your model
- Submit your work on time by the project deadline: Friday, April 28, 9:00 am
- [BONUS] Change the decision threshold for positive labels using predicted probabilities
- [BONUS] Examine precision-recall instead of accuracy/ROC curves
- [BONUS] Construct bagging classifiers on the data

**Pro Tip:** Here are some questions to keep in mind:

- What are we looking for? What is the hypothesis?
- How can we train the model?
- What is the overall goal of this research project?

---

### Requirements

- A Jupyter Notebook with the required problem statement, goals, and technical data. Include a written cell that discusses the accuracy and assumptions of your model.
- Create a blog post of at least 500 words (and 1-2 graphics!) describing your data, analysis, and approach.

---
### Necessary Deliverables / Submission

- Code must be in a clearly labeled Jupyter notebook.
- Materials must be pushed to your GitHub repo and posted to your blog.
- Materials must be submitted by the start of class on Friday, April 28.

---


### Dataset

Your data is stored within an AWS Postgres remote database.

We have imported the Titanic data into an AWS PostgreSQL instance, which you can find by connecting here:

    host: dsi.c20gkj5cvu3l.us-east-1.rds.amazonaws.com
    port: 5432
    username: dsi_student
    database: titanic
    password: gastudents

You can use a python library like pandas, sqlalchemy, or psycopg to import the data locally.

---


### Useful Resources

- [Documentation for Logistic Regression in Python](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)
- [PostgreSQl and Python](https://wiki.postgresql.org/wiki/Psycopg2_Tutorial)

---

#### Project Feedback + Evaluation

[Attached here is a complete rubric for this project.](./project-05-rubric.md)

Your instructors will score each of your technical requirements using the scale below:

    Score | Expectations
    ----- | ------------
    **0** | _Incomplete._
    **1** | _Does not meet expectations._
    **2** | _Meets expectations, good job!_
    **3** | _Exceeds expectations, you wonderful creature, you!_

 This will serve as a helpful overall gauge of whether you met the project goals, but __the more important scores are the individual ones__ above, which can help you identify where to focus your efforts for the next project!
