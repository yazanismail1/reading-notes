# Data Visualization

Data visualization is an interdisciplinary field that deals with the graphic representation of data and information. It is a particularly efficient way of communicating when the data or information is numerous as for example a time series.

**How to visualize data?**

There are multiple libraries that offer data visualization in which most of them are built upon matplotlib library.

**What is Matplotlib?**

Matplotlib is the "grandfather" library of data visualization with Python. It was created by John Hunter. He created it to try to replicate MatLab's (another programming language) plotting capabilities in Python. Matplotlib is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality figures in many formats.

**Why to use matplotlib?**

- Generally easy to get started for simple plots

- Support for custom labels and texts

- Great control of every element in a figure

- High-quality output in many formats

- Very customizable in general

Matplotlib allows you to create reproducible figures programmatically.

**Installing Matplotlib**

```
pip install matplotlib
```
**Importing and using matplotlib**

```
import matplotlib.pyplot as plt # Importing it
%matplotlib inline # to see plots in the notebook
```

**Examples**

```
plt.plot(x, y, 'r') 

# The previous line of code is used to plot a simple line connecting the point given.
# 'r' is the color red of the line

plt.xlabel('X Axis Title Here')
plt.ylabel('Y Axis Title Here')
plt.title('String Title Here')

# The previous lines is to have a X-label, Y-label and a title for the plot.

plt.show()

# The previous lines is to plot the result.

fig.savefig("filename.png", dpi=200)

# The previous lines is save the plot as an image.
# We can also optionally specify the DPI and choose between different output formats
# We can also add the attribute legend of create a legend in our plot.

.legend(loc=1) # upper right corner
.legend(loc=2) # upper left corner
.legend(loc=3) # lower left corner
.legend(loc=4) # lower right corner
.legend(loc=0) # let matplotlib decide the optimal location

# The previous lines is to choose the location where we want to place the legend on out plot.

# We can also pass a color, linewidth, alpha attributes to control the colors, line width and opacity level of the plotted lines.
```

**Plot Types**

```
plt.scatter(x,y) # scatter plot
plt.hist(data) # histogram plot
plt.boxplot(data,vert=True,patch_artist=True) # box plot
```

Plot Types: https://matplotlib.org/stable/gallery/index.html

**Example Output**

![](https://matplotlib.org/stable/_images/sphx_glr_filled_step_001.png)

---

**Seaborn**

Seaborn is a library for making statistical graphics in Python. It builds on top of matplotlib and integrates closely with pandas data structures.

Seaborn helps you explore and understand your data. Its plotting functions operate on dataframes and arrays containing whole datasets and internally perform the necessary semantic mapping and statistical aggregation to produce informative plots. Its dataset-oriented, declarative API lets you focus on what the different elements of your plots mean, rather than on the details of how to draw them.

**Installing and Importing Seaborn**

```
pip install seaborn
import seaborn as sns
```

Plot Types : https://seaborn.pydata.org/examples/index.html

**Example Output**

![](https://seaborn.pydata.org/_images/introduction_1_0.png)

---

**Bokeh**

Bokeh is an interactive visualization library that targets modern web browsers for presentation. It is good for:

- Interactive visualization in modern browsers
- Standalone HTML documents, or server-backed apps
- Expressive and versatile graphics
- Large, dynamic or streaming data
- Easy usage from python (or Scala, or R, or...)
- And most importantly: NO JAVASCRIPT REQUIRED

Bokeh is an interactive visualization library for modern web browsers. It provides elegant, concise construction of versatile graphics, and affords high-performance interactivity over large or streaming datasets. Bokeh can help anyone who would like to quickly and easily make interactive plots, dashboards, and data applications.

**Standard Imports**

```
from bokeh.io import output_notebook, show
output_notebook()
```

**Example Output**

When hovering over each histogram bar it gives you additional information.

![](Capture.png)

---

**Cheat Sheets and Handouts**

Matplotlib : https://matplotlib.org/cheatsheets/

Seaborn: https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf

Seaborn: https://www.kaggle.com/code/themlphdstudent/cheat-sheet-seaborn-charts

Bokeh: https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Bokeh_Cheat_Sheet.pdf

---

## Things I want to know more about

- Data Science and Analysis

---

## References

[1] https://hub.gke2.mybinder.org/user/bokeh-bokeh-notebooks-lfeydw7q/notebooks/tutorial/00%20-%20Introduction%20and%20Setup.ipynb

[2] https://seaborn.pydata.org/index.html

[3] https://matplotlib.org/stable/
