# Filtering
- Used to select a rows in a dataFrame that satisfy a condition
- Boolean Masking
	- A condition is applied to a column which return true or false
```
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie", "David"],
    "Age": [24, 30, 22, 35],
    "City": ["NY", "LA", "NY", "SF"]
}

df = pd.DataFrame(data)
filt = (df['Age']>25)
print(filt)
print("---------------------------------------------------------")
print(df[filt])
print("---------------------------------------------------------")
```
```
Output:
0    False
1     True
2    False
3     True
Name: Age, dtype: bool
---------------------------------------------------------
    Name  Age City
1    Bob   30   LA
3  David   35   SF
---------------------------------------------------------
```
- Multiple Conditions
	- `&` - And
	- `|` - Or
	- `~` - Not
```
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie", "David"],
    "Age": [24, 30, 22, 35],
    "City": ["NY", "LA", "NY", "SF"]
}

df = pd.DataFrame(data)
filt_1 = ((df['Age']>25) & (df['City']=="LA"))
print(df[filt_1])
print("---------------------------------------------------------")
print(df[~filt_1])
print("---------------------------------------------------------")
```
```
Output:
  Name  Age City
1  Bob   30   LA
---------------------------------------------------------
      Name  Age City
0    Alice   24   NY
2  Charlie   22   NY
3    David   35   SF
---------------------------------------------------------
```
- Use of `.isin()`
	- Take rows where city is either SF or LA
```
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie", "David"],
    "Age": [24, 30, 22, 35],
    "City": ["NY", "LA", "NY", "SF"]
}

df = pd.DataFrame(data)
filt_1 = (df['City'].isin(["SF","LA"]))
print(df[filt_1])

```
```
Output:
    Name  Age City
1    Bob   30   LA
3  David   35   SF
```
- Use `.str` methods
```
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie", "David"],
    "Age": [24, 30, 22, 35],
    "City": ["NY", "LA", "NY", "SF"]
}

df = pd.DataFrame(data)
filt_1 = (df['Name'].str.startswith("B"))
print(df[filt_1])

```
```
Output:
  Name  Age City
1  Bob   30   LA
```
- Filtering with. query
```
filtered = df.query("Age > 25 and City == 'NY'")
```
- Filtering with `.loc`
```
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie", "David"],
    "Age": [24, 30, 22, 35],
    "City": ["NY", "LA", "NY", "SF"]
}

df = pd.DataFrame(data)
filt_1 = (df['Name'].str.startswith("B"))
print(df.loc[filt_1, ['Name','Age']])
```
```
Output:
  Name  Age
1  Bob   30
```
