
In this project, I will be exploring the SAT score data from 2001. The data represents the average SAT score for all 50 states, including average participating rate, Average math, and verbal score. The goal of this project is to do some exploratory data analysis(EDA) along with a summary using basic Python programming and data visualization. I will also try to find some other interesting insights and demonstrate it using visualization tools like Matplotlab, Plotly and Tableau.  

# Importing Modules & Data


```python
## importing pandas library
import pandas as pd

## importing numpy library
import numpy as np

## importing pyplot from matplotlib inorder to do data visualization. 
from matplotlib import pyplot as plt

## these modules are imported to use plotly. 
import plotly.plotly as py
import plotly.graph_objs as go

## matplotlib inline helps showing graphs in jupyter notebook. 
%matplotlib inline

## import data as a dataframe from a local file, open it, read it and assign it to "data"
data = pd.read_csv("/Users/masumrumi/dsi-nyc-5/projects/project-1-sat-scores/assets/sat_scores.csv")
data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>State</th>
      <th>Rate</th>
      <th>Verbal</th>
      <th>Math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CT</td>
      <td>82</td>
      <td>509</td>
      <td>510</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NJ</td>
      <td>81</td>
      <td>499</td>
      <td>513</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MA</td>
      <td>79</td>
      <td>511</td>
      <td>515</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NY</td>
      <td>77</td>
      <td>495</td>
      <td>505</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NH</td>
      <td>72</td>
      <td>520</td>
      <td>516</td>
    </tr>
  </tbody>
</table>
</div>



## Exploratory Data Analysis (EDA)

While doing Exploratory Data Analysis, I will try to elaborate the process by approaching the process in Manually and using python's built in functions. 


```python
## Take a look at the whole dataset
data
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>State</th>
      <th>Rate</th>
      <th>Verbal</th>
      <th>Math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CT</td>
      <td>82</td>
      <td>509</td>
      <td>510</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NJ</td>
      <td>81</td>
      <td>499</td>
      <td>513</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MA</td>
      <td>79</td>
      <td>511</td>
      <td>515</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NY</td>
      <td>77</td>
      <td>495</td>
      <td>505</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NH</td>
      <td>72</td>
      <td>520</td>
      <td>516</td>
    </tr>
    <tr>
      <th>5</th>
      <td>RI</td>
      <td>71</td>
      <td>501</td>
      <td>499</td>
    </tr>
    <tr>
      <th>6</th>
      <td>PA</td>
      <td>71</td>
      <td>500</td>
      <td>499</td>
    </tr>
    <tr>
      <th>7</th>
      <td>VT</td>
      <td>69</td>
      <td>511</td>
      <td>506</td>
    </tr>
    <tr>
      <th>8</th>
      <td>ME</td>
      <td>69</td>
      <td>506</td>
      <td>500</td>
    </tr>
    <tr>
      <th>9</th>
      <td>VA</td>
      <td>68</td>
      <td>510</td>
      <td>501</td>
    </tr>
    <tr>
      <th>10</th>
      <td>DE</td>
      <td>67</td>
      <td>501</td>
      <td>499</td>
    </tr>
    <tr>
      <th>11</th>
      <td>MD</td>
      <td>65</td>
      <td>508</td>
      <td>510</td>
    </tr>
    <tr>
      <th>12</th>
      <td>NC</td>
      <td>65</td>
      <td>493</td>
      <td>499</td>
    </tr>
    <tr>
      <th>13</th>
      <td>GA</td>
      <td>63</td>
      <td>491</td>
      <td>489</td>
    </tr>
    <tr>
      <th>14</th>
      <td>IN</td>
      <td>60</td>
      <td>499</td>
      <td>501</td>
    </tr>
    <tr>
      <th>15</th>
      <td>SC</td>
      <td>57</td>
      <td>486</td>
      <td>488</td>
    </tr>
    <tr>
      <th>16</th>
      <td>DC</td>
      <td>56</td>
      <td>482</td>
      <td>474</td>
    </tr>
    <tr>
      <th>17</th>
      <td>OR</td>
      <td>55</td>
      <td>526</td>
      <td>526</td>
    </tr>
    <tr>
      <th>18</th>
      <td>FL</td>
      <td>54</td>
      <td>498</td>
      <td>499</td>
    </tr>
    <tr>
      <th>19</th>
      <td>WA</td>
      <td>53</td>
      <td>527</td>
      <td>527</td>
    </tr>
    <tr>
      <th>20</th>
      <td>TX</td>
      <td>53</td>
      <td>493</td>
      <td>499</td>
    </tr>
    <tr>
      <th>21</th>
      <td>HI</td>
      <td>52</td>
      <td>485</td>
      <td>515</td>
    </tr>
    <tr>
      <th>22</th>
      <td>AK</td>
      <td>51</td>
      <td>514</td>
      <td>510</td>
    </tr>
    <tr>
      <th>23</th>
      <td>CA</td>
      <td>51</td>
      <td>498</td>
      <td>517</td>
    </tr>
    <tr>
      <th>24</th>
      <td>AZ</td>
      <td>34</td>
      <td>523</td>
      <td>525</td>
    </tr>
    <tr>
      <th>25</th>
      <td>NV</td>
      <td>33</td>
      <td>509</td>
      <td>515</td>
    </tr>
    <tr>
      <th>26</th>
      <td>CO</td>
      <td>31</td>
      <td>539</td>
      <td>542</td>
    </tr>
    <tr>
      <th>27</th>
      <td>OH</td>
      <td>26</td>
      <td>534</td>
      <td>439</td>
    </tr>
    <tr>
      <th>28</th>
      <td>MT</td>
      <td>23</td>
      <td>539</td>
      <td>539</td>
    </tr>
    <tr>
      <th>29</th>
      <td>WV</td>
      <td>18</td>
      <td>527</td>
      <td>512</td>
    </tr>
    <tr>
      <th>30</th>
      <td>ID</td>
      <td>17</td>
      <td>543</td>
      <td>542</td>
    </tr>
    <tr>
      <th>31</th>
      <td>TN</td>
      <td>13</td>
      <td>562</td>
      <td>553</td>
    </tr>
    <tr>
      <th>32</th>
      <td>NM</td>
      <td>13</td>
      <td>551</td>
      <td>542</td>
    </tr>
    <tr>
      <th>33</th>
      <td>IL</td>
      <td>12</td>
      <td>576</td>
      <td>589</td>
    </tr>
    <tr>
      <th>34</th>
      <td>KY</td>
      <td>12</td>
      <td>550</td>
      <td>550</td>
    </tr>
    <tr>
      <th>35</th>
      <td>WY</td>
      <td>11</td>
      <td>547</td>
      <td>545</td>
    </tr>
    <tr>
      <th>36</th>
      <td>MI</td>
      <td>11</td>
      <td>561</td>
      <td>572</td>
    </tr>
    <tr>
      <th>37</th>
      <td>MN</td>
      <td>9</td>
      <td>580</td>
      <td>589</td>
    </tr>
    <tr>
      <th>38</th>
      <td>KS</td>
      <td>9</td>
      <td>577</td>
      <td>580</td>
    </tr>
    <tr>
      <th>39</th>
      <td>AL</td>
      <td>9</td>
      <td>559</td>
      <td>554</td>
    </tr>
    <tr>
      <th>40</th>
      <td>NE</td>
      <td>8</td>
      <td>562</td>
      <td>568</td>
    </tr>
    <tr>
      <th>41</th>
      <td>OK</td>
      <td>8</td>
      <td>567</td>
      <td>561</td>
    </tr>
    <tr>
      <th>42</th>
      <td>MO</td>
      <td>8</td>
      <td>577</td>
      <td>577</td>
    </tr>
    <tr>
      <th>43</th>
      <td>LA</td>
      <td>7</td>
      <td>564</td>
      <td>562</td>
    </tr>
    <tr>
      <th>44</th>
      <td>WI</td>
      <td>6</td>
      <td>584</td>
      <td>596</td>
    </tr>
    <tr>
      <th>45</th>
      <td>AR</td>
      <td>6</td>
      <td>562</td>
      <td>550</td>
    </tr>
    <tr>
      <th>46</th>
      <td>UT</td>
      <td>5</td>
      <td>575</td>
      <td>570</td>
    </tr>
    <tr>
      <th>47</th>
      <td>IA</td>
      <td>5</td>
      <td>593</td>
      <td>603</td>
    </tr>
    <tr>
      <th>48</th>
      <td>SD</td>
      <td>4</td>
      <td>577</td>
      <td>582</td>
    </tr>
    <tr>
      <th>49</th>
      <td>ND</td>
      <td>4</td>
      <td>592</td>
      <td>599</td>
    </tr>
    <tr>
      <th>50</th>
      <td>MS</td>
      <td>4</td>
      <td>566</td>
      <td>551</td>
    </tr>
    <tr>
      <th>51</th>
      <td>All</td>
      <td>45</td>
      <td>506</td>
      <td>514</td>
    </tr>
  </tbody>
</table>
</div>



This is a small dataset and good for any rookie learners like me who want to get their hands dirty in the process of learning data science. There are no missing values and no errors, though I have noticed that the last row for State column has the value of "All", which I assume is the mean of all 50 states. I will remove this row for a better understanding of the data and visualization. 

## EDA using built-in python functions


```python
# Inplace means to commit the changes to the DataFrame
# The 'All' row is at index 51
data.drop(51, inplace=True)

# Displaying the last five rows to see if the last row was removed. 
data.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>State</th>
      <th>Rate</th>
      <th>Verbal</th>
      <th>Math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>46</th>
      <td>UT</td>
      <td>5</td>
      <td>575</td>
      <td>570</td>
    </tr>
    <tr>
      <th>47</th>
      <td>IA</td>
      <td>5</td>
      <td>593</td>
      <td>603</td>
    </tr>
    <tr>
      <th>48</th>
      <td>SD</td>
      <td>4</td>
      <td>577</td>
      <td>582</td>
    </tr>
    <tr>
      <th>49</th>
      <td>ND</td>
      <td>4</td>
      <td>592</td>
      <td>599</td>
    </tr>
    <tr>
      <th>50</th>
      <td>MS</td>
      <td>4</td>
      <td>566</td>
      <td>551</td>
    </tr>
  </tbody>
</table>
</div>




```python
data.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 51 entries, 0 to 50
    Data columns (total 4 columns):
    State     51 non-null object
    Rate      51 non-null int64
    Verbal    51 non-null int64
    Math      51 non-null int64
    dtypes: int64(3), object(1)
    memory usage: 2.0+ KB



```python
## Checking to see if there are any null values that I may have missed.
data.isnull().sum()
```




    State     0
    Rate      0
    Verbal    0
    Math      0
    dtype: int64




```python
data.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rate</th>
      <th>Verbal</th>
      <th>Math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>37.000000</td>
      <td>532.529412</td>
      <td>531.843137</td>
    </tr>
    <tr>
      <th>std</th>
      <td>27.550681</td>
      <td>33.360667</td>
      <td>36.287393</td>
    </tr>
    <tr>
      <th>min</th>
      <td>4.000000</td>
      <td>482.000000</td>
      <td>439.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>9.000000</td>
      <td>501.000000</td>
      <td>503.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>33.000000</td>
      <td>527.000000</td>
      <td>525.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>64.000000</td>
      <td>562.000000</td>
      <td>557.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>82.000000</td>
      <td>593.000000</td>
      <td>603.000000</td>
    </tr>
  </tbody>
</table>
</div>



The 

## EDA using raw coding


```python
## Converting DataFrame into list
data_list = data.values.tolist()
##data_list = data.values.T.tolist()
```

I am going to create a dictionary where the key would be each headers and the values would be the value of the column assigned to each of the headers. This is a good approach if we want to work with big data since dictionary is a fast and can store multiple types at a time. 


```python
## first I will get the headers to that I can assigned them to keys of the dictionary. 
headers = data.columns

## Creating an alternative dictionary in order to 
another_dict = {}
another_dict[headers[1]] = [item[1] for item in data_list]
another_dict[headers[2]] = [item[2] for item in data_list]
another_dict[headers[3]] = [item[3] for item in data_list]
```


```python
## The following code pring the Min and Max of Rate, Math and Verbal. 
for i in range(len(another_dict.keys())):
    print "Min of", another_dict.keys()[i], "is:", min(another_dict[another_dict.keys()[i]])
    print "and Max of", another_dict.keys()[i], "is:", max(another_dict[another_dict.keys()[i]])
```


      File "<ipython-input-10-270b78d876d3>", line 3
        print "Min of", another_dict.keys()[i], "is:", min(another_dict[another_dict.keys()[i])
                     ^
    SyntaxError: invalid syntax




```python
## Writting function using only list comprehensions, no loops, to compute Standard Deviation as a part of practice. 
def std_dev(a_list):
    n = len(a_list)
    m = sum(a_list)/n
    
    std = (sum([(item-m)**2 for item in a_list])/float(n))**0.5
    return std


## Apply the function above to find the Standard Deviation for Rate, Math and Verbal. 
print "The Standard Deviation of Rate is: {}".format(std_dev(another_dict["Rate"]))
print "The Standard Deviation of Math is: {}".format(std_dev(another_dict["Math"]))
print "The Standard Deviation of Verbal is: {}".format(std_dev(another_dict["Verbal"]))
```

## Visualization of the data

Visualization is one of the core componemt of data science and it is personally my favorite. For this summary analysis I will use plotly. Plotly is interective, really easy to use and fun to work with.


```python
x = data.Rate
data1 = [go.Histogram(x=x)];
layout = go.Layout(
    title = "Histogram #1: Distribution of Participation Rate", 
    
    xaxis = dict(
        title = "Score"
    ),
    yaxis = dict(
        title = "Frequency"
    ),
    bargap = 0.01

)
fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='basic histogram')
```


```python
x = data.Math
data1 = [go.Histogram(x=x)];
layout = go.Layout(
    title = "Histogram #2: Distribution of Math", 
    
    xaxis = dict(
        title = "Score"
    ),
    yaxis = dict(
        title = "Frequency"
    ),
    bargap = 0.01

)
fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='basic histogram1')
```


```python
x = data.Verbal
data2 = [go.Histogram(x=x)];
layout = go.Layout(
    title = "Histogram #3: Distribution of Verbal", 
    
    xaxis = dict(
        title = "Score"
    ),
    yaxis = dict(
        title = "Frequency"
    ),
    bargap = 0.01
)
fig = go.Figure(data = data2, layout = layout)
py.iplot(fig, filename='basic histogram2')
```

Now let's create an overlaid histgram to compare between verbal and Math


```python
xv = data.Verbal
xm = data.Math

trace1 = go.Histogram(
    x = xv,
    name = "Verbal", 
    opacity = 0.75,
    #autobinx =False,

)
trace2 = go.Histogram(
    x = xm, 
    name = "Math", 
    opacity = 0.75,
    #autobinx = False
)

data2 = [trace1, trace2]
layout = go.Layout(
    title = "Histogram #4: Distribution of both Math and Verbal", 
    
    xaxis = dict(
        title = "Score"
    ),
    yaxis = dict(
        title = "Frequency"
    ),
    bargap = 0.01,
    #bargroupgap = 0.1,
    barmode="overlay")

fig = go.Figure(data = data2, layout = layout)
py.iplot(fig, filename = "overlaid histogram")
```

### Histogram Analysis

The typical assumption is for data distribution is to follow a normal distribution. However, if we look at the overlaid histogram above, we can see that none of the histograms look like a normal distribution. The only data that seems to be closest to a normal distribution is math score distribution. The distribution for the participation rate seems to be positively skewed since lots of states are not participating enough. 



```python
# Create a trace
trace = go.Scatter(
    x = data.Verbal,
    y = data.Math,
    name = "Math",
    mode = 'markers'
)

# Create a layout with title, xaxis and yaxis
layout = go.Layout(
    title = "Scatter plot #1: Math Scores vs Verbal Scores",
    xaxis = dict(title = "Verbal"),
    yaxis = dict(title = "Math")
)
data1 = [trace]

# Plot and embed in ipython notebook!
fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='basic-scatter1')

# or plot with: plot_url = py.plot(data, filename='basic-line')
```


```python
# Create a trace
trace = go.Scatter(
    x = data.Rate,
    y = data.Math,
    name = "Math",
    mode = 'markers'
)

# Create a layout with title, xaxis and yaxis
layout = go.Layout(
    title = "Scatter plot #2: Math Score vs Participation Rate",
    xaxis = dict(title = "Participation Rate"),
    yaxis = dict(title = "Math Score")
)
data1 = [trace]

# Plot and embed in ipython notebook!
fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='basic-scatter2')

# or plot with: plot_url = py.plot(data, filename='basic-line')
```


```python
# Create a trace
trace = go.Scatter(
    x = data.Rate,
    y = data.Verbal,
    name = "Verbal",
    mode = 'markers'
)

# Create a layout with title, xaxis and yaxis
layout = go.Layout(
    title = "Scatter plot #3: Verbal Score vs Participation Rate",
    xaxis = dict(title = "Participation Rate"),
    yaxis = dict(title = "Math Score")
)
data1 = [trace]

# Plot and embed in ipython notebook!
fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='basic-scatter3')

# or plot with: plot_url = py.plot(data, filename='basic-line')
```


```python
# Create a trace
trace = go.Scatter(
    x = data.Rate,
    y = data.Math,
    name = "Math",
    mode = 'markers'
)
trace1 = go.Scatter(
    x = data.Rate,
    y = data.Verbal,
    name = "Verbal",
    mode = "markers"

)

# Create a layout with title, xaxis and yaxis
layout = go.Layout(
    title = "Scatter plot #4: Math and Verbal Score vs Participation Rate",
    xaxis = dict(title = "Participation Rate"),
    yaxis = dict(title = "Math and Verbal Score")
)
data1 = [trace, trace1]

# Plot and embed in ipython notebook!
fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='basic-scatter4')

# or plot with: plot_url = py.plot(data, filename='basic-line')
```

### Scatterplot Analysis

Scatterplots are great in analyzing relationships between two variables.  We can get whole different sets of insights by looking at the data using scatterplots. For example, by looking at the scatter plots we see that There are some interesting correlations between Math and verbal scores.

States that score higher in Math also score higher in Verbal. One particularly interesting thing is that, States with low participation rate scores comparatively higher than states with high participation rate. This is likely due to some smartest students who self-select to take SAT where the colleges do not require to take SAT. Lastly, there is an outlier in the scatter plot above where the state Ohio's math sat score is 439 and the verbal score is 534. In this situation, math score is much lower than verbal score which may be normal for some students but not for a whole state.


```python
x0 = data.Rate

Rate = go.Box(y=x0, name = "Rate", boxpoints = "all")
data1 = [Rate]
layout = go.Layout(
    title = "Boxplot #1: Boxplot for Participation Rates of 50 States",
)

fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='boxplot_1')


```


```python
x0 = data.Math
x1 = data.Verbal

Math = go.Box(y=x0, name = "Math", boxpoints = "all")
Verbal = go.Box(y=x1, name = "Verbal", boxpoints = "all", marker = dict(color = 'rgb(10, 128, 128)'))
data1 = [Math, Verbal]
layout = go.Layout(
    title = "Boxplot #2: Boxplot for Math and Verbal Score distrubution",
)

fig = go.Figure(data = data1, layout = layout)
py.iplot(fig, filename='boxplot_2')

```

### Boxplot Analysis

If we look at boxplot #1 we would see that the rate data is positively skewed. Of course, we have already known that from histogram #1. However, this boxplot #1 reveals some interesting facts since we have aligned all the points along with the boxplot. If we hover our mouse over the boxplot we can see that the middle quartile or median line is not in the center of the filled rectangle which means there is more data between median and upper quartile than the median and lower quartile, in other words, positive skewness. 

Boxplot #2 also reveals some interesting insights about SAT math and verbal score distributions. first of all, we can see why the lower whisker is so far way and we already know it is because of the outlier 439. If we ignore the outlier and try to visualize the boxplot #2, we would probably see similar boxplots representing math and verbal. However, with the outlier, the boxplot shows a somewhat symmetrical shape of math scores which proves the point from histogram analysis, that math score shows a somewhat normal distribution. As for verbal distribution, the boxplot shows a small positive skewness. This is not discernable with the histogram since the histogram does not show any recognizable pattern of skewness.

# Tableau Data Visualization

![title](../assets/Sat_verbal.png)

![title](../assets/Sat_math.png)

### Tableau Visualization Analysis

The heatmap above was created using Tableau. The heatmap shows that east coast and west coast states score significantly lower than the middle states in both math and verbal even though the middle states have lower participation rate. It seems like there is a negative correlation between rate and math or rate and verbal. 
