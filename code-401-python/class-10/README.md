# Linear Regression

Regression searches for relationships among variables, where it explores the relationship between a quantitine response variable and one or more explanatory variable. For example, you can observe several employees of some company and try to understand how their salaries depend on their features, such as experience, education level, role, city of employment, and so on.

**When Do You Need Regression?**

You need regression to answer whether and how some phenomenon influences the other or how several variables are related.

![](https://files.realpython.com/media/fig-lin-reg.a506035b654a.png)

**Types of Regression**

- **Simple Linear Regression**

Simple or single-variate linear regression is the simplest case of linear regression, as it has a single independent variable.

- **Multiple Linear Regression**

Multiple or multivariate linear regression is a case of linear regression with two or more independent variables.

- **Polynomial Regression**

A generalized case of linear regression. You assume the polynomial dependence between the output and inputs and, consequently, the polynomial estimated regression function.

In other words, in addition to linear terms like 𝑏₁𝑥₁, your regression function 𝑓 can include nonlinear terms such as 𝑏₂𝑥₁², 𝑏₃𝑥₁³, or even 𝑏₄𝑥₁𝑥₂, 𝑏₅𝑥₁²𝑥₂.

**Implimenting Linear Regression in Python**

There are several ways in which you can do that, you can do linear regression using numpy, scipy, stats model and sckit learn.

Why **Scikit-learn**?

Scikit-learn is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction.

**Steps for Implementing Linear Regression**

1. Import libraries, data and clean it.

2. Explore data and rename columns as desired.

3. Explore data set using .DESCR.

4. Use Scikit learn to fit linear regression to the entire data set and calculated the mean squared error.

5. Make a train-test split and calculated the mean squared error for my training data and test data.

6. Plot the residuals for my training and test datasets.

---

## Things I want to know more about

- Data Science

---

## References

[1] Manu Jeevan, Mar 5, 2018 _How to run Linear regression in Python scikit-Learn_, accessed 22 October 2022, <https://www.crayondata.com/how-to-run-linear-regression-in-python-scikit-learn/>

[2] Mirko Stojiljković, May 16, 2022 _HLinear Regression in Python_, accessed 22 October 2022, <https://realpython.com/linear-regression-in-python/#what-is-regression>

[3] jbstatistics, Dec 6, 2012 _Introduction to Simple Linear Regression_, accessed 22 October 2022, <https://www.youtube.com/watch?v=KsVBBJRb9TE&list=PLvxOuBpazmsND0vmkP1ECjTloiVz-pXla>
