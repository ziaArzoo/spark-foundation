EXPLORATORY DATA ANALYSIS

By :** MD ZIA ARZOO **
data science and business analytics intern @The spark foundation

Dataset: https://bit.ly/3i4rbWl

#GRIPAUGUST21 #TSF #DATASCIENCE


[ ]
%matplotlib inline
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

[ ]
url = 'https://raw.githubusercontent.com/ziaArzoo/spark-foundation/main/SampleSuperstore%20(1).csv'
df1 = pd.read_csv(url)

[ ]
df1.head()


[ ]
df1.info()
df1.isnull().sum()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 9994 entries, 0 to 9993
Data columns (total 13 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   Ship Mode     9994 non-null   object 
 1   Segment       9994 non-null   object 
 2   Country       9994 non-null   object 
 3   City          9994 non-null   object 
 4   State         9994 non-null   object 
 5   Postal Code   9994 non-null   int64  
 6   Region        9994 non-null   object 
 7   Category      9994 non-null   object 
 8   Sub-Category  9994 non-null   object 
 9   Sales         9994 non-null   float64
 10  Quantity      9994 non-null   int64  
 11  Discount      9994 non-null   float64
 12  Profit        9994 non-null   float64
dtypes: float64(3), int64(2), object(8)
memory usage: 1015.1+ KB
Ship Mode       0
Segment         0
Country         0
City            0
State           0
Postal Code     0
Region          0
Category        0
Sub-Category    0
Sales           0
Quantity        0
Discount        0
Profit          0
dtype: int64

[ ]
df1.shape

(9994, 13)

[ ]
df1.columns
Index(['Ship Mode', 'Segment', 'Country', 'City', 'State', 'Postal Code',
       'Region', 'Category', 'Sub-Category', 'Sales', 'Quantity', 'Discount',
       'Profit'],
      dtype='object')
Analysis


[ ]
plt.figure(figsize=(8,5))
sns.kdeplot(df1['Sales'],color='green',label='Sales',shade=True)
sns.kdeplot(df1['Profit'],color='Blue',label='Profit',shade=True)
plt.xlim([-100,1000])
plt.legend()

It can be seen that profit has direct relation with sales increases profit increases although the profit margin per sale in few reigns are not same as other, so it can be increased

Realtion between diffrent column with individual columns

Category


[ ]
sns.pairplot(df1,hue='Category')


** Reign**


[ ]
sns.pairplot(df1,hue='Region')



[ ]
sns.pairplot(df1,hue='Segment')


Correlation between diffrent columns


[ ]
df1.corr()


***Heatmap ***


[ ]
sns.heatmap(df1.corr(),cmap='rocket_r',annot=True)


plot for subcategories


[ ]
plt.figure(figsize=(20,8))
sns.countplot(df1['Sub-Category'])
plt.title('Sub-Category',fontsize=20)

Statewise deals


[ ]
df2 = df1['State'].value_counts()
df2.head(10)
California        2001
New York          1128
Texas              985
Pennsylvania       587
Washington         506
Illinois           492
Ohio               469
Florida            383
Michigan           255
North Carolina     249
Name: State, dtype: int64

[ ]
df2.plot(kind='bar',figsize=(15,5))
plt.ylabel('Frequency / Number of deals')
plt.xlabel('States')

plt.title('State Wise Dealings', fontsize = 20)
plt.show()

Here is top 3 state where deals are highest

Califonia

New York

Texas

Wyoming: Lowest Number of deal


[ ]
df1['State'].value_counts().mean()

203.9591836734694
average deal per state is approx 204

Statewise profits


[ ]

df1['State'].value_counts().head(10)

California        2001
New York          1128
Texas              985
Pennsylvania       587
Washington         506
Illinois           492
Ohio               469
Florida            383
Michigan           255
North Carolina     249
Name: State, dtype: int64

[ ]
df_state= df1.groupby(['State'])[['Sales', 'Discount', 'Profit']].mean()
df_state.head(10)


[ ]
df_state1=df_state.sort_values('Profit')

df_state1[['Profit']].plot(kind = 'bar', figsize = (15,4))
plt.title('State wise Profit Analysis', fontsize = 20)
plt.ylabel('Profit per Sate')
plt.xlabel('States')
plt.show()


RESULT

Vermont: Highest Profit

Ohio: Lowest Profit

citywise analysis


[ ]
df2 = df['City'].value_counts()
df2=df2.head(50

[ ]
df2.plot(kind='bar',figsize=(15,5))
plt.ylabel('Frequency / Number of deals')
plt.xlabel('City')

plt.title('City Wise Dealings', fontsize = 20)
plt.show()

Here is top 3 city where deals are Highest.

New York City
Los Angeles
Philadelphia

[ ]
df1['City'].value_counts().mean()
18.821092278719398
Average deals per city is 19


[ ]
df1_quantity = df1.groupby(['Quantity'])[['Sales', 'Discount', 'Profit']].mean()
df1_quantity.head(10)

** Quantity wise sales profit and Discount**


[ ]
#1. sales 2. Discount 3. Profit
df1_quantity.plot.pie(subplots=True, 
                    autopct='%1.1f%%',
                    figsize=(20, 20),
                     pctdistance=0.69,
                    startangle=90,     # start angle 90° (Africa)
                    shadow=True,
                    labels = df1_quantity.index)
plt.title('Quantity wise analysis of Sale, Discount, profit')

Category wise analysis


[ ]
df_category = df1.groupby(['Category'])[['Sales', 'Discount', 'Profit']].mean()
df_category


[ ]
df_category.plot.pie(subplots=True, 
                     figsize=(18, 20), 
                     autopct='%1.1f%%', 
                     labels = df_category.index)

Maximun sales and Profit obtain in Technology. Minimun profit obtain in Furniture

Ship mode wise Analysis


[ ]
df1['Ship Mode'].value_counts()

Standard Class    5968
Second Class      1945
First Class       1538
Same Day           543
Name: Ship Mode, dtype: int64

[ ]
df_shipmode = df1.groupby(['Ship Mode'])[['Sales', 'Discount', 'Profit']].mean()
df_shipmode.plot.pie(subplots=True,
                     figsize=(18, 20), 
                     autopct='%1.1f%%', 
                     labels = df_shipmode.index)

Profit and Discount is high in First Class

Sales is high for Same day ship

Double-click (or enter) to edit

Final Insights
Profit is more than that of sale but there are some areas where profit could be increased.

Profit and Discount is high in First Class

Sales is high for Same day ship

Category: Maximun sales and Profit obtain in Technology.

Category: Minimun profit obtain in Furniture

State: Vermont: Highest Profit

State: Ohio: Lowest Profit

Segment: Home-office: High Profit & sales

Here is top 3 city where deals are Highest.

New York City

Los Angeles

Philadelphia

Sales and Profit are Moderately Correlated.

Quantity and Profit are less Moderately Correlated.

Discount and Profit are Negatively Correlated

Here is top 3 state where deals are Highest.

Califonia

New York

Texas

