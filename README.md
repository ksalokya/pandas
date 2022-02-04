<div align="center">
  <img src="https://github.com/ksalokya/devicon/blob/master/icons/pandas/pandas-original-wordmark.svg" width="300px"/>
</div>
<h1 align="center">pandas Cheatsheet</h1>

## What is pandas?
#### The pandas library is built on NumPy and provides easy-to-use data structures and data analysis tools for the Python programming language.

## Installing pandas
```
  pip install pandas
```

# pandas Basics


```python
import numpy as np
import pandas as pd
```


```python
# Dataframe
df = pd.DataFrame()
print(df)
```

    Empty DataFrame
    Columns: []
    Index: []
    


```python
df1 = pd.DataFrame([[1,2,3,4],[5,6,7,8],[2,7,3,23],[3,6,8,23],[23,23,63,12]])

# Show Dataframe1
df1
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>12</td>
    </tr>
  </tbody>
</table>




```python
# head function
df1.head()
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>12</td>
    </tr>
  </tbody>
</table>




```python
# show top 3
df1.head(3)
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23</td>
    </tr>
  </tbody>
</table>




```python
# tail function
df1.tail()
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>12</td>
    </tr>
  </tbody>
</table>




```python
# show bottom 3
df1.tail(3)
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>12</td>
    </tr>
  </tbody>
</table>



# Slicing and Adding Columns


```python
# columns should always be equal to len of columns of DataFrame
df2 = pd.DataFrame([[1,2,3,4],[5,6,7,8],[2,7,3,23],[3,6,8,23],[23,23,63,12]],columns=['A1', 'B2', 'C', 'D'])
```


```python
df2
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A1</th>
      <th>B2</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>12</td>
    </tr>
  </tbody>
</table>




```python
df2.shape
```




    (5, 4)




```python
# slicing
df1.iloc[0,1]
```




    2




```python
df1.iloc[0:2,0:2]
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
    </tr>
  </tbody>
</table>



# Reading a CSV File


```python
df = pd.read_csv('stocks.csv')
```


```python
df.head(5)
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SYMBOL</th>
      <th>SERIES</th>
      <th>DATE1</th>
      <th>PREV_CLOSE</th>
      <th>OPEN_PRICE</th>
      <th>HIGH_PRICE</th>
      <th>LOW_PRICE</th>
      <th>LAST_PRICE</th>
      <th>CLOSE_PRICE</th>
      <th>AVG_PRICE</th>
      <th>TTL_TRD_QNTY</th>
      <th>TURNOVER_LACS</th>
      <th>NO_OF_TRADES</th>
      <th>DELIV_QTY</th>
      <th>DELIV_PER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20MICRONS</td>
      <td>EQ</td>
      <td>03-Feb-2022</td>
      <td>90.90</td>
      <td>91.65</td>
      <td>93.70</td>
      <td>89.50</td>
      <td>91.00</td>
      <td>90.60</td>
      <td>91.21</td>
      <td>260677</td>
      <td>237.76</td>
      <td>4001</td>
      <td>105320</td>
      <td>40.40</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21STCENMGM</td>
      <td>EQ</td>
      <td>03-Feb-2022</td>
      <td>42.90</td>
      <td>42.05</td>
      <td>42.05</td>
      <td>42.05</td>
      <td>42.05</td>
      <td>42.05</td>
      <td>42.05</td>
      <td>3341</td>
      <td>1.40</td>
      <td>47</td>
      <td>3341</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3IINFOLTD</td>
      <td>EQ</td>
      <td>03-Feb-2022</td>
      <td>77.35</td>
      <td>77.35</td>
      <td>78.40</td>
      <td>76.60</td>
      <td>76.90</td>
      <td>76.90</td>
      <td>77.22</td>
      <td>374402</td>
      <td>289.11</td>
      <td>4000</td>
      <td>270957</td>
      <td>72.37</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3MINDIA</td>
      <td>EQ</td>
      <td>03-Feb-2022</td>
      <td>24982.75</td>
      <td>25221.50</td>
      <td>25221.50</td>
      <td>24520.80</td>
      <td>24580.00</td>
      <td>24868.65</td>
      <td>24879.35</td>
      <td>3570</td>
      <td>888.19</td>
      <td>2078</td>
      <td>1882</td>
      <td>52.72</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3PLAND</td>
      <td>BE</td>
      <td>03-Feb-2022</td>
      <td>18.70</td>
      <td>19.00</td>
      <td>19.60</td>
      <td>19.00</td>
      <td>19.60</td>
      <td>19.60</td>
      <td>19.55</td>
      <td>4268</td>
      <td>0.83</td>
      <td>60</td>
      <td>-</td>
      <td>-</td>
    </tr>
  </tbody>
</table>




```python
print(df['SYMBOL'].dtype)
```

    object
    

# Writing a CSV File


```python
df2 = pd.DataFrame([[1,3,4],[5,6,7,8],[2,7,3,23],[3,6,8,23],[23,23,63]],columns=['A', 'B', 'C', 'D'])
print(df2)
```

        A   B   C     D
    0   1   3   4   NaN
    1   5   6   7   8.0
    2   2   7   3  23.0
    3   3   6   8  23.0
    4  23  23  63   NaN
    


```python
df2.to_csv('export.csv')
df3 = pd.read_csv('export.csv')
df3
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>1</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>




```python
# indexing is False
df2.to_csv('export.csv',index=False)
df4 = pd.read_csv('export.csv')
df4
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>23.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>6</td>
      <td>8</td>
      <td>23.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>23</td>
      <td>63</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>



# Merging DataFrames


```python
df5 = pd.DataFrame([[1,2,3],[5,6,7],[2,7,3]], columns=['A','B','C'])
df5
```



<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
    </tr>
  </tbody>
</table>




```python
df6 = pd.DataFrame([[11,2,31],[22,8,35],[63,7,92]], columns=['X','Y','Z'])
df6
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>11</td>
      <td>2</td>
      <td>31</td>
    </tr>
    <tr>
      <th>1</th>
      <td>22</td>
      <td>8</td>
      <td>35</td>
    </tr>
    <tr>
      <th>2</th>
      <td>63</td>
      <td>7</td>
      <td>92</td>
    </tr>
  </tbody>
</table>




```python
# merge those rows & columns
# whose col-B of df5 has
# same value as of col-Y of df6
df7 = pd.merge(df5,df6,left_on='B',right_on='Y')
df7
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>11</td>
      <td>2</td>
      <td>31</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>63</td>
      <td>7</td>
      <td>92</td>
    </tr>
  </tbody>
</table>




```python

```


## Tutorial 
[Pandas Tutorial](https://youtu.be/RhEjmHeDNoA)
