```python
import pandas as pd 
df = pd.read_csv('./customer_shopping_behavior.csv')
```


```python
df.head()
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
      <th>Customer ID</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item Purchased</th>
      <th>Category</th>
      <th>Purchase Amount (USD)</th>
      <th>Location</th>
      <th>Size</th>
      <th>Color</th>
      <th>Season</th>
      <th>Review Rating</th>
      <th>Subscription Status</th>
      <th>Shipping Type</th>
      <th>Discount Applied</th>
      <th>Promo Code Used</th>
      <th>Previous Purchases</th>
      <th>Payment Method</th>
      <th>Frequency of Purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>55</td>
      <td>Male</td>
      <td>Blouse</td>
      <td>Clothing</td>
      <td>53</td>
      <td>Kentucky</td>
      <td>L</td>
      <td>Gray</td>
      <td>Winter</td>
      <td>3.1</td>
      <td>Yes</td>
      <td>Express</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>14</td>
      <td>Venmo</td>
      <td>Fortnightly</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>19</td>
      <td>Male</td>
      <td>Sweater</td>
      <td>Clothing</td>
      <td>64</td>
      <td>Maine</td>
      <td>L</td>
      <td>Maroon</td>
      <td>Winter</td>
      <td>3.1</td>
      <td>Yes</td>
      <td>Express</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>2</td>
      <td>Cash</td>
      <td>Fortnightly</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>50</td>
      <td>Male</td>
      <td>Jeans</td>
      <td>Clothing</td>
      <td>73</td>
      <td>Massachusetts</td>
      <td>S</td>
      <td>Maroon</td>
      <td>Spring</td>
      <td>3.1</td>
      <td>Yes</td>
      <td>Free Shipping</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>23</td>
      <td>Credit Card</td>
      <td>Weekly</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>21</td>
      <td>Male</td>
      <td>Sandals</td>
      <td>Footwear</td>
      <td>90</td>
      <td>Rhode Island</td>
      <td>M</td>
      <td>Maroon</td>
      <td>Spring</td>
      <td>3.5</td>
      <td>Yes</td>
      <td>Next Day Air</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>49</td>
      <td>PayPal</td>
      <td>Weekly</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>45</td>
      <td>Male</td>
      <td>Blouse</td>
      <td>Clothing</td>
      <td>49</td>
      <td>Oregon</td>
      <td>M</td>
      <td>Turquoise</td>
      <td>Spring</td>
      <td>2.7</td>
      <td>Yes</td>
      <td>Free Shipping</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>31</td>
      <td>PayPal</td>
      <td>Annually</td>
    </tr>
  </tbody>
</table>
</div>




```python
# structure
df.info()
# Review Rating - 3863 non-null   float64
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 3900 entries, 0 to 3899
    Data columns (total 18 columns):
     #   Column                  Non-Null Count  Dtype  
    ---  ------                  --------------  -----  
     0   Customer ID             3900 non-null   int64  
     1   Age                     3900 non-null   int64  
     2   Gender                  3900 non-null   object 
     3   Item Purchased          3900 non-null   object 
     4   Category                3900 non-null   object 
     5   Purchase Amount (USD)   3900 non-null   int64  
     6   Location                3900 non-null   object 
     7   Size                    3900 non-null   object 
     8   Color                   3900 non-null   object 
     9   Season                  3900 non-null   object 
     10  Review Rating           3863 non-null   float64
     11  Subscription Status     3900 non-null   object 
     12  Shipping Type           3900 non-null   object 
     13  Discount Applied        3900 non-null   object 
     14  Promo Code Used         3900 non-null   object 
     15  Previous Purchases      3900 non-null   int64  
     16  Payment Method          3900 non-null   object 
     17  Frequency of Purchases  3900 non-null   object 
    dtypes: float64(1), int64(4), object(13)
    memory usage: 548.6+ KB
    


```python
# summary statistics
df.describe() # numerical columns 
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
      <th>Customer ID</th>
      <th>Age</th>
      <th>Purchase Amount (USD)</th>
      <th>Review Rating</th>
      <th>Previous Purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3900.000000</td>
      <td>3900.000000</td>
      <td>3900.000000</td>
      <td>3863.000000</td>
      <td>3900.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1950.500000</td>
      <td>44.068462</td>
      <td>59.764359</td>
      <td>3.750065</td>
      <td>25.351538</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1125.977353</td>
      <td>15.207589</td>
      <td>23.685392</td>
      <td>0.716983</td>
      <td>14.447125</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>18.000000</td>
      <td>20.000000</td>
      <td>2.500000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>975.750000</td>
      <td>31.000000</td>
      <td>39.000000</td>
      <td>3.100000</td>
      <td>13.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1950.500000</td>
      <td>44.000000</td>
      <td>60.000000</td>
      <td>3.800000</td>
      <td>25.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2925.250000</td>
      <td>57.000000</td>
      <td>81.000000</td>
      <td>4.400000</td>
      <td>38.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3900.000000</td>
      <td>70.000000</td>
      <td>100.000000</td>
      <td>5.000000</td>
      <td>50.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe(include = 'all') # all columns
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
      <th>Customer ID</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item Purchased</th>
      <th>Category</th>
      <th>Purchase Amount (USD)</th>
      <th>Location</th>
      <th>Size</th>
      <th>Color</th>
      <th>Season</th>
      <th>Review Rating</th>
      <th>Subscription Status</th>
      <th>Shipping Type</th>
      <th>Discount Applied</th>
      <th>Promo Code Used</th>
      <th>Previous Purchases</th>
      <th>Payment Method</th>
      <th>Frequency of Purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3900.000000</td>
      <td>3900.000000</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900.000000</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3863.000000</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900.000000</td>
      <td>3900</td>
      <td>3900</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2</td>
      <td>25</td>
      <td>4</td>
      <td>NaN</td>
      <td>50</td>
      <td>4</td>
      <td>25</td>
      <td>4</td>
      <td>NaN</td>
      <td>2</td>
      <td>6</td>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>top</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Male</td>
      <td>Blouse</td>
      <td>Clothing</td>
      <td>NaN</td>
      <td>Montana</td>
      <td>M</td>
      <td>Olive</td>
      <td>Spring</td>
      <td>NaN</td>
      <td>No</td>
      <td>Free Shipping</td>
      <td>No</td>
      <td>No</td>
      <td>NaN</td>
      <td>PayPal</td>
      <td>Every 3 Months</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2652</td>
      <td>171</td>
      <td>1737</td>
      <td>NaN</td>
      <td>96</td>
      <td>1755</td>
      <td>177</td>
      <td>999</td>
      <td>NaN</td>
      <td>2847</td>
      <td>675</td>
      <td>2223</td>
      <td>2223</td>
      <td>NaN</td>
      <td>677</td>
      <td>584</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1950.500000</td>
      <td>44.068462</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>59.764359</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.750065</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>25.351538</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1125.977353</td>
      <td>15.207589</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>23.685392</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.716983</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>14.447125</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>18.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.500000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>975.750000</td>
      <td>31.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>39.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.100000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1950.500000</td>
      <td>44.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>60.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.800000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>25.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2925.250000</td>
      <td>57.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>81.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4.400000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>38.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3900.000000</td>
      <td>70.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>100.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>50.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# missing values
df.isnull().sum()
# Review Rating  37
```




    Customer ID                0
    Age                        0
    Gender                     0
    Item Purchased             0
    Category                   0
    Purchase Amount (USD)      0
    Location                   0
    Size                       0
    Color                      0
    Season                     0
    Review Rating             37
    Subscription Status        0
    Shipping Type              0
    Discount Applied           0
    Promo Code Used            0
    Previous Purchases         0
    Payment Method             0
    Frequency of Purchases     0
    dtype: int64



# handle missing values
## fill with median over mean -
  * mean can get affected by the outliers and that can skew the distribution of the data
  * median is robust to outliers
  * median of each category -> to avoid bias into the dataset


```python
df['Review Rating'] = df.groupby('Category')['Review Rating'].transform(lambda x: x.fillna(x.median()))
```


```python
df.isnull().sum()
```




    Customer ID               0
    Age                       0
    Gender                    0
    Item Purchased            0
    Category                  0
    Purchase Amount (USD)     0
    Location                  0
    Size                      0
    Color                     0
    Season                    0
    Review Rating             0
    Subscription Status       0
    Shipping Type             0
    Discount Applied          0
    Promo Code Used           0
    Previous Purchases        0
    Payment Method            0
    Frequency of Purchases    0
    dtype: int64




```python
# modify - snake casing - easy referencing of code in sql / python
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
df = df.rename(columns = {'purchase_amount_(usd)' : 'purchase_amount_usd'})
```


```python
df.columns
```




    Index(['customer_id', 'age', 'gender', 'item_purchased', 'category',
           'purchase_amount_usd', 'location', 'size', 'color', 'season',
           'review_rating', 'subscription_status', 'shipping_type',
           'discount_applied', 'promo_code_used', 'previous_purchases',
           'payment_method', 'frequency_of_purchases'],
          dtype='object')



## feature enginnering - create new columns



```python
# create column - age_group
label = ['Young Adult', 'Adult', 'Middle-aged', 'Senior']
df['age_group'] = pd.qcut(df['age'], q = 4, labels = label)
```


```python
df[['age', 'age_group']].head(10)
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
      <th>age</th>
      <th>age_group</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>55</td>
      <td>Middle-aged</td>
    </tr>
    <tr>
      <th>1</th>
      <td>19</td>
      <td>Young Adult</td>
    </tr>
    <tr>
      <th>2</th>
      <td>50</td>
      <td>Middle-aged</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>Young Adult</td>
    </tr>
    <tr>
      <th>4</th>
      <td>45</td>
      <td>Middle-aged</td>
    </tr>
    <tr>
      <th>5</th>
      <td>46</td>
      <td>Middle-aged</td>
    </tr>
    <tr>
      <th>6</th>
      <td>63</td>
      <td>Senior</td>
    </tr>
    <tr>
      <th>7</th>
      <td>27</td>
      <td>Young Adult</td>
    </tr>
    <tr>
      <th>8</th>
      <td>26</td>
      <td>Young Adult</td>
    </tr>
    <tr>
      <th>9</th>
      <td>57</td>
      <td>Middle-aged</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['frequency_of_purchases'].unique()
```




    array(['Fortnightly', 'Weekly', 'Annually', 'Quarterly', 'Bi-Weekly',
           'Monthly', 'Every 3 Months'], dtype=object)




```python
# create column - purchase_frequency_days - numbers
frequency_mapping = {
    'Fortnightly': 14,
    'Weekly': 7,
    'Annually': 365,
    'Quarterly': 90,
    'Bi-Weekly': 14,
    'Monthly': 30,
    'Every 3 Months': 90
}
# now handling inconsistencies is not req.

df['purchase_frequency_days'] = df['frequency_of_purchases'].map(frequency_mapping)
```


```python
df[['frequency_of_purchases', 'purchase_frequency_days']].head(10)
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
      <th>frequency_of_purchases</th>
      <th>purchase_frequency_days</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Fortnightly</td>
      <td>14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Fortnightly</td>
      <td>14</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Weekly</td>
      <td>7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Weekly</td>
      <td>7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Annually</td>
      <td>365</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Weekly</td>
      <td>7</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Quarterly</td>
      <td>90</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Weekly</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Annually</td>
      <td>365</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Quarterly</td>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>




```python
# handling redundency
df[['discount_applied', 'promo_code_used']]
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
      <th>discount_applied</th>
      <th>promo_code_used</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3895</th>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <th>3896</th>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <th>3897</th>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <th>3898</th>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <th>3899</th>
      <td>No</td>
      <td>No</td>
    </tr>
  </tbody>
</table>
<p>3900 rows × 2 columns</p>
</div>




```python
bool((df['discount_applied'] == df['promo_code_used']).all())
```




    True




```python
df = df.drop('promo_code_used', axis = 1)
```


```python
df.columns
```




    Index(['customer_id', 'age', 'gender', 'item_purchased', 'category',
           'purchase_amount_usd', 'location', 'size', 'color', 'season',
           'review_rating', 'subscription_status', 'shipping_type',
           'discount_applied', 'previous_purchases', 'payment_method',
           'frequency_of_purchases', 'age_group', 'purchase_frequency_days'],
          dtype='object')



## Connecting Python script to MySQL


```python
!pip install pymysql sqlalchemy
```

    Requirement already satisfied: pymysql in c:\users\alkapoddar\anaconda3\lib\site-packages (1.2.0)
    Requirement already satisfied: sqlalchemy in c:\users\alkapoddar\anaconda3\lib\site-packages (2.0.43)
    Requirement already satisfied: greenlet>=1 in c:\users\alkapoddar\anaconda3\lib\site-packages (from sqlalchemy) (3.2.4)
    Requirement already satisfied: typing-extensions>=4.6.0 in c:\users\alkapoddar\anaconda3\lib\site-packages (from sqlalchemy) (4.15.0)
    


```python
from sqlalchemy import create_engine
from urllib.parse import quote_plus
import pandas as pd

username = "root"
password = quote_plus("mysql@alka")   # encode special chars
host = "localhost"
port = "3306"
database = "customer_behavior"

engine = create_engine(
    f"mysql+pymysql://{username}:{password}@{host}:{port}/{database}"
)

# Write dataframe
df.to_sql("customer", engine, if_exists="replace", index=False)

# Read sample
pd.read_sql("SELECT * FROM customer LIMIT 10;", engine)
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
      <th>customer_id</th>
      <th>age</th>
      <th>gender</th>
      <th>item_purchased</th>
      <th>category</th>
      <th>purchase_amount_usd</th>
      <th>location</th>
      <th>size</th>
      <th>color</th>
      <th>season</th>
      <th>review_rating</th>
      <th>subscription_status</th>
      <th>shipping_type</th>
      <th>discount_applied</th>
      <th>previous_purchases</th>
      <th>payment_method</th>
      <th>frequency_of_purchases</th>
      <th>age_group</th>
      <th>purchase_frequency_days</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>55</td>
      <td>Male</td>
      <td>Blouse</td>
      <td>Clothing</td>
      <td>53</td>
      <td>Kentucky</td>
      <td>L</td>
      <td>Gray</td>
      <td>Winter</td>
      <td>3.1</td>
      <td>Yes</td>
      <td>Express</td>
      <td>Yes</td>
      <td>14</td>
      <td>Venmo</td>
      <td>Fortnightly</td>
      <td>Middle-aged</td>
      <td>14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>19</td>
      <td>Male</td>
      <td>Sweater</td>
      <td>Clothing</td>
      <td>64</td>
      <td>Maine</td>
      <td>L</td>
      <td>Maroon</td>
      <td>Winter</td>
      <td>3.1</td>
      <td>Yes</td>
      <td>Express</td>
      <td>Yes</td>
      <td>2</td>
      <td>Cash</td>
      <td>Fortnightly</td>
      <td>Young Adult</td>
      <td>14</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>50</td>
      <td>Male</td>
      <td>Jeans</td>
      <td>Clothing</td>
      <td>73</td>
      <td>Massachusetts</td>
      <td>S</td>
      <td>Maroon</td>
      <td>Spring</td>
      <td>3.1</td>
      <td>Yes</td>
      <td>Free Shipping</td>
      <td>Yes</td>
      <td>23</td>
      <td>Credit Card</td>
      <td>Weekly</td>
      <td>Middle-aged</td>
      <td>7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>21</td>
      <td>Male</td>
      <td>Sandals</td>
      <td>Footwear</td>
      <td>90</td>
      <td>Rhode Island</td>
      <td>M</td>
      <td>Maroon</td>
      <td>Spring</td>
      <td>3.5</td>
      <td>Yes</td>
      <td>Next Day Air</td>
      <td>Yes</td>
      <td>49</td>
      <td>PayPal</td>
      <td>Weekly</td>
      <td>Young Adult</td>
      <td>7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>45</td>
      <td>Male</td>
      <td>Blouse</td>
      <td>Clothing</td>
      <td>49</td>
      <td>Oregon</td>
      <td>M</td>
      <td>Turquoise</td>
      <td>Spring</td>
      <td>2.7</td>
      <td>Yes</td>
      <td>Free Shipping</td>
      <td>Yes</td>
      <td>31</td>
      <td>PayPal</td>
      <td>Annually</td>
      <td>Middle-aged</td>
      <td>365</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>46</td>
      <td>Male</td>
      <td>Sneakers</td>
      <td>Footwear</td>
      <td>20</td>
      <td>Wyoming</td>
      <td>M</td>
      <td>White</td>
      <td>Summer</td>
      <td>2.9</td>
      <td>Yes</td>
      <td>Standard</td>
      <td>Yes</td>
      <td>14</td>
      <td>Venmo</td>
      <td>Weekly</td>
      <td>Middle-aged</td>
      <td>7</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>63</td>
      <td>Male</td>
      <td>Shirt</td>
      <td>Clothing</td>
      <td>85</td>
      <td>Montana</td>
      <td>M</td>
      <td>Gray</td>
      <td>Fall</td>
      <td>3.2</td>
      <td>Yes</td>
      <td>Free Shipping</td>
      <td>Yes</td>
      <td>49</td>
      <td>Cash</td>
      <td>Quarterly</td>
      <td>Senior</td>
      <td>90</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>27</td>
      <td>Male</td>
      <td>Shorts</td>
      <td>Clothing</td>
      <td>34</td>
      <td>Louisiana</td>
      <td>L</td>
      <td>Charcoal</td>
      <td>Winter</td>
      <td>3.2</td>
      <td>Yes</td>
      <td>Free Shipping</td>
      <td>Yes</td>
      <td>19</td>
      <td>Credit Card</td>
      <td>Weekly</td>
      <td>Young Adult</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>26</td>
      <td>Male</td>
      <td>Coat</td>
      <td>Outerwear</td>
      <td>97</td>
      <td>West Virginia</td>
      <td>L</td>
      <td>Silver</td>
      <td>Summer</td>
      <td>2.6</td>
      <td>Yes</td>
      <td>Express</td>
      <td>Yes</td>
      <td>8</td>
      <td>Venmo</td>
      <td>Annually</td>
      <td>Young Adult</td>
      <td>365</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>57</td>
      <td>Male</td>
      <td>Handbag</td>
      <td>Accessories</td>
      <td>31</td>
      <td>Missouri</td>
      <td>M</td>
      <td>Pink</td>
      <td>Spring</td>
      <td>4.8</td>
      <td>Yes</td>
      <td>2-Day Shipping</td>
      <td>Yes</td>
      <td>4</td>
      <td>Cash</td>
      <td>Quarterly</td>
      <td>Middle-aged</td>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```
