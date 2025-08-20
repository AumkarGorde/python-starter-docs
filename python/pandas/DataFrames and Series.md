# DataFrame and Series
- We can think of a dataFrame as a rows and columns
- Series can be think as a rows of a single column
- DataFrame can be termed as a container of multiple series object

#### Convert to dataFrame
- Converting a dictionary to dataFrame
- Access a columns
	- `df['email'] or df.email` both gives the same result
- Access a multiple columns
	- `df[['name','email']]` 
- Get all the columns
	- `df.columns`
- Get the rows by integer location
	- `df.iloc[1]`
	- `df.iloc[[0,1]]` - get 2 rows 
	- `df.iloc[[0,1], 2]` - get only email for the 2 rows (0,1)
- Get the rows by labels
	- `df.loc['0']` - where 0 is a label not index
	- `df.loc[['0','1'],'email']` - get 2 rows and one column of email
	- `df.loc[['0','1'],['email','lastname']]`
- Slicing
	- `df.loc[0:2, 'email']` - get 2 rows with email columns
	- `df.loc[0:2, 'lastname':'email']`
```
import pandas as pd

person = {
    'name' : ['Omkar', 'John', 'Sunil'],
    'lastname': ['Gorde', 'Abhraham', 'Chetri'],
    'email' : ['ogorde@abc.com','jabhraham@abc.com','schetri@abc.com']
}

df = pd.DataFrame(person)

print('---------------------------------------------------------')
print(df)
print('---------------------------------------------------------')
print(df['email'])
print('---------------------------------------------------------')
print(df.email)
```
```
Output:
---------------------------------------------------------
    name  lastname              email
0  Omkar     Gorde     ogorde@abc.com
1   John  Abhraham  jabhraham@abc.com
2  Sunil    Chetri    schetri@abc.com
---------------------------------------------------------
0       ogorde@abc.com
1    jabhraham@abc.com
2      schetri@abc.com
Name: email, dtype: object
---------------------------------------------------------
0       ogorde@abc.com
1    jabhraham@abc.com
2      schetri@abc.com
Name: email, dtype: object
```

