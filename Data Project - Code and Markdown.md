# Final Project - Code and Markdown 

***Niamh Herbert***

For my final project, I wanted to look at where disabled people stand in Ireland's housing crisis. To do this, I looked at Census data from the most recent collection (2016) and where it reported that disabled people are living.

***

## 1. First dataset: Where do Persons with Disabilities Live?

My first dataframe was aquired from data on the National Disability Authority website, which originated from the 2016 Census. But before I can upload my small dataset, I need to import **pandas**


```python
import pandas as pd 
```


```python
df = pd.read_csv('C:/Users/niamh/Downloads/Where do Disabled People Live 2016.csv')
```


```python
df
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
      <th>Settlement</th>
      <th>Gen Pop</th>
      <th>Pop with Disabilities</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Private Households</td>
      <td>97.37%</td>
      <td>92.90%</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Living Alone (Private Households)</td>
      <td>8.50%</td>
      <td>19.30%</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Communal Establishments</td>
      <td>2.63%</td>
      <td>7.07%</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Homeless</td>
      <td>0.14%</td>
      <td>0.29%</td>
    </tr>
  </tbody>
</table>
</div>



This dataframe did not reuire tidying or cleaning, so I could get straight to plotting 

### 1.1 Plotting and Visualisation 


```python
import pygal
from pygal.style import Style
```


```python
bar_chart = pygal.HorizontalBar()
bar_chart.title = 'Where do Persons with Disabilities Live? (in%)'
bar_chart.add('Private Households', 92.90)
bar_chart.add('Communal Establishments', 7.07)
bar_chart.add('Homeless', 0.29)

bar_chart.render_in_browser()
```

    file://C:/Users/niamh/AppData/Local/Temp/tmpg6otwix7.html
    


```python
pie_chart = pygal.Pie()
pie_chart.title = 'Where do Persons with Disabilities Live? (in %)'
pie_chart.add('Private Households', 92.90)
pie_chart.add('Communal Establishmentd', 7.07)
pie_chart.add('Homeless', 0.29)

pie_chart.render_in_browser()
```

    file://C:/Users/niamh/AppData/Local/Temp/tmpuwiaqly9.html
    

I wanted to create bothe a bar chart and a pie chart for this visualisation so I culd seen which was more intuitive to read. I will opt to use the pie chart in my final product but I will export and put the data into Datawrapper because of its alt text description feature which makes the graph more accessible to people who use screen readers.

The visualisation I created can be found here: https://datawrapper.dwcdn.net/UihTG/1/

***

## 2. Second dataset: Homeless Persons with One or More Disabilities, 2016 and 2011

For ths section of my project, I found data on data.gov.ie from the 2016 and 2011 Censuses
First, I'll deal with the 2016 data:


```python
df2016 = pd.read_csv('C:/Users/niamh/Downloads/E5014.20221212T151201.csv')
```


```python
df2016
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
      <th>Statistic Label</th>
      <th>Sex</th>
      <th>Type of Disability</th>
      <th>CensusYear</th>
      <th>UNIT</th>
      <th>VALUE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Total persons</td>
      <td>2016</td>
      <td>Number</td>
      <td>6906</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Total persons with a disability</td>
      <td>2016</td>
      <td>Number</td>
      <td>1871</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2016</td>
      <td>Number</td>
      <td>158</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2016</td>
      <td>Number</td>
      <td>131</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2016</td>
      <td>Number</td>
      <td>581</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>An intellectual disability</td>
      <td>2016</td>
      <td>Number</td>
      <td>213</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2016</td>
      <td>Number</td>
      <td>621</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Psychological or emotional condition</td>
      <td>2016</td>
      <td>Number</td>
      <td>825</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Other disability, including chronic illness</td>
      <td>2016</td>
      <td>Number</td>
      <td>840</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2016</td>
      <td>Number</td>
      <td>246</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Difficulty in going outside home alone</td>
      <td>2016</td>
      <td>Number</td>
      <td>362</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2016</td>
      <td>Number</td>
      <td>619</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Difficulty in participating in other activities</td>
      <td>2016</td>
      <td>Number</td>
      <td>509</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Both sexes</td>
      <td>Total disabilities</td>
      <td>2016</td>
      <td>Number</td>
      <td>5105</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Total persons</td>
      <td>2016</td>
      <td>Number</td>
      <td>4018</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Total persons with a disability</td>
      <td>2016</td>
      <td>Number</td>
      <td>1222</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2016</td>
      <td>Number</td>
      <td>119</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2016</td>
      <td>Number</td>
      <td>89</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2016</td>
      <td>Number</td>
      <td>401</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>An intellectual disability</td>
      <td>2016</td>
      <td>Number</td>
      <td>145</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2016</td>
      <td>Number</td>
      <td>402</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Psychological or emotional condition</td>
      <td>2016</td>
      <td>Number</td>
      <td>514</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Other disability, including chronic illness</td>
      <td>2016</td>
      <td>Number</td>
      <td>541</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2016</td>
      <td>Number</td>
      <td>155</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Difficulty in going outside home alone</td>
      <td>2016</td>
      <td>Number</td>
      <td>218</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2016</td>
      <td>Number</td>
      <td>429</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Difficulty in participating in other activities</td>
      <td>2016</td>
      <td>Number</td>
      <td>351</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Male</td>
      <td>Total disabilities</td>
      <td>2016</td>
      <td>Number</td>
      <td>3364</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Total persons</td>
      <td>2016</td>
      <td>Number</td>
      <td>2888</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Total persons with a disability</td>
      <td>2016</td>
      <td>Number</td>
      <td>649</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2016</td>
      <td>Number</td>
      <td>39</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2016</td>
      <td>Number</td>
      <td>42</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2016</td>
      <td>Number</td>
      <td>180</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>An intellectual disability</td>
      <td>2016</td>
      <td>Number</td>
      <td>68</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2016</td>
      <td>Number</td>
      <td>219</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Psychological or emotional condition</td>
      <td>2016</td>
      <td>Number</td>
      <td>311</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Other disability, including chronic illness</td>
      <td>2016</td>
      <td>Number</td>
      <td>299</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2016</td>
      <td>Number</td>
      <td>91</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Difficulty in going outside home alone</td>
      <td>2016</td>
      <td>Number</td>
      <td>144</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2016</td>
      <td>Number</td>
      <td>190</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Difficulty in participating in other activities</td>
      <td>2016</td>
      <td>Number</td>
      <td>158</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Female</td>
      <td>Total disabilities</td>
      <td>2016</td>
      <td>Number</td>
      <td>1741</td>
    </tr>
  </tbody>
</table>
</div>



This data frame is too long, so I'll drop lines 13-41 because I don't think they are relevant to what I want to include in my project.


```python
df2016_1 = df2016.iloc[0:13]
#adf1 = adf.drop([13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41])
```

I also want to drop the 'UNIT' and 'Sex' columns from my dataframe because I do not want to incluse a gender breakdown in my final product


```python
df2016_1 = df2016_1.drop(['UNIT', 'Sex'], axis=1)
```


```python
df2016_1
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
      <th>Statistic Label</th>
      <th>Type of Disability</th>
      <th>CensusYear</th>
      <th>VALUE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Total persons</td>
      <td>2016</td>
      <td>6906</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Total persons with a disability</td>
      <td>2016</td>
      <td>1871</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2016</td>
      <td>158</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2016</td>
      <td>131</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2016</td>
      <td>581</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>An intellectual disability</td>
      <td>2016</td>
      <td>213</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2016</td>
      <td>621</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Psychological or emotional condition</td>
      <td>2016</td>
      <td>825</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Other disability, including chronic illness</td>
      <td>2016</td>
      <td>840</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2016</td>
      <td>246</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in going outside home alone</td>
      <td>2016</td>
      <td>362</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2016</td>
      <td>619</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in participating in other activities</td>
      <td>2016</td>
      <td>509</td>
    </tr>
  </tbody>
</table>
</div>



I will now move on to my second dataframe, this one from the 2011 Census


```python
df2011 = pd.read_csv('C:/Users/niamh/Downloads/PEH12.20221212T181254.csv')
```


```python
df2011
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
      <th>Statistic Label</th>
      <th>Type of Disability</th>
      <th>CensusYear</th>
      <th>UNIT</th>
      <th>VALUE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total persons</td>
      <td>2011</td>
      <td>Number</td>
      <td>3808</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total persons with a disability</td>
      <td>2011</td>
      <td>Number</td>
      <td>1581</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2011</td>
      <td>Number</td>
      <td>140</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2011</td>
      <td>Number</td>
      <td>144</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2011</td>
      <td>Number</td>
      <td>492</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>An intellectual disability</td>
      <td>2011</td>
      <td>Number</td>
      <td>214</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2011</td>
      <td>Number</td>
      <td>532</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Psychological or emotional condition</td>
      <td>2011</td>
      <td>Number</td>
      <td>740</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Other disability, including chronic illness</td>
      <td>2011</td>
      <td>Number</td>
      <td>697</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2011</td>
      <td>Number</td>
      <td>180</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in going outside home alone</td>
      <td>2011</td>
      <td>Number</td>
      <td>277</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2011</td>
      <td>Number</td>
      <td>578</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in participating in other activities</td>
      <td>2011</td>
      <td>Number</td>
      <td>408</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total disabilities</td>
      <td>2011</td>
      <td>Number</td>
      <td>4402</td>
    </tr>
  </tbody>
</table>
</div>



As you can see, this dataframe has similar elements to the 2016 one, but has no 'Sex' clumn
I will remove the 'UNIT' column and row number 13 to make it more similar to out 2016 dataframe


```python
df2011 = df2011.drop([13])
```


```python
df2011
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
      <th>Statistic Label</th>
      <th>Type of Disability</th>
      <th>CensusYear</th>
      <th>UNIT</th>
      <th>VALUE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total persons</td>
      <td>2011</td>
      <td>Number</td>
      <td>3808</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total persons with a disability</td>
      <td>2011</td>
      <td>Number</td>
      <td>1581</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2011</td>
      <td>Number</td>
      <td>140</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2011</td>
      <td>Number</td>
      <td>144</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2011</td>
      <td>Number</td>
      <td>492</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>An intellectual disability</td>
      <td>2011</td>
      <td>Number</td>
      <td>214</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2011</td>
      <td>Number</td>
      <td>532</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Psychological or emotional condition</td>
      <td>2011</td>
      <td>Number</td>
      <td>740</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Other disability, including chronic illness</td>
      <td>2011</td>
      <td>Number</td>
      <td>697</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2011</td>
      <td>Number</td>
      <td>180</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in going outside home alone</td>
      <td>2011</td>
      <td>Number</td>
      <td>277</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2011</td>
      <td>Number</td>
      <td>578</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in participating in other activities</td>
      <td>2011</td>
      <td>Number</td>
      <td>408</td>
    </tr>
  </tbody>
</table>
</div>



Now I will combine my two datasets into one 


```python
df_comb = pd.concat([df2016_1, df2011],axis=0).reset_index(drop=True)
del df_comb['UNIT']
```


```python
df_comb
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
      <th>Statistic Label</th>
      <th>Type of Disability</th>
      <th>CensusYear</th>
      <th>VALUE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Total persons</td>
      <td>2016</td>
      <td>6906</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Total persons with a disability</td>
      <td>2016</td>
      <td>1871</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2016</td>
      <td>158</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2016</td>
      <td>131</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2016</td>
      <td>581</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>An intellectual disability</td>
      <td>2016</td>
      <td>213</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2016</td>
      <td>621</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Psychological or emotional condition</td>
      <td>2016</td>
      <td>825</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Other disability, including chronic illness</td>
      <td>2016</td>
      <td>840</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2016</td>
      <td>246</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in going outside home alone</td>
      <td>2016</td>
      <td>362</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2016</td>
      <td>619</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Homeless Persons with One or More Disabilities...</td>
      <td>Difficulty in participating in other activities</td>
      <td>2016</td>
      <td>509</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total persons</td>
      <td>2011</td>
      <td>3808</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Total persons with a disability</td>
      <td>2011</td>
      <td>1581</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Blindness or a serious vision impairment</td>
      <td>2011</td>
      <td>140</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Deafness or a serious hearing impairment</td>
      <td>2011</td>
      <td>144</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>A condition that substantially limits one or m...</td>
      <td>2011</td>
      <td>492</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>An intellectual disability</td>
      <td>2011</td>
      <td>214</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in learning, remembering or concent...</td>
      <td>2011</td>
      <td>532</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Psychological or emotional condition</td>
      <td>2011</td>
      <td>740</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Other disability, including chronic illness</td>
      <td>2011</td>
      <td>697</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in dressing, bathing or getting aro...</td>
      <td>2011</td>
      <td>180</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in going outside home alone</td>
      <td>2011</td>
      <td>277</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in working or attending school/college</td>
      <td>2011</td>
      <td>578</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Homeless Persons with One or More Disabilities</td>
      <td>Difficulty in participating in other activities</td>
      <td>2011</td>
      <td>408</td>
    </tr>
  </tbody>
</table>
</div>



This data is now ready to be plotted.

### 2.1 Plotting and Visualisation

As with the previous dataframe, I will export and put the data into Datawrapper because of its alt text description feature which akes the graph accessible to people who use screen readers.

The visualisation I created can be found here: https://datawrapper.dwcdn.net/T6NW6/1/

I chose to use variations of the colour purple in both of my visualisations because purple is the colour for disability awareness. Using Datawrapper's features, I was able to check the accessibility of these colour choices for people with visual impairments.
