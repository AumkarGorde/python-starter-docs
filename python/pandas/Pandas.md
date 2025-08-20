# Pandas
#### Installing pandas
- Use command : `poetry add pandas`
- Install Jupyter notebook : `poetry add jupyterlab`
	- Run `jupyter notebook`
		- This will run Jupyter notebook on one of the ports
	- Inside this create a notebook
#### Basics
- Reading a csv file : `df = pd.read_csv('file_path')`
- Shape attribute : Gives details about rows and columns `(rows, columns)`
	- `df.shape`
- `df.info()`  - Gives no. of rows and columns and also data type
- `pd.set_option('display.max_columns',85)` - print 85 columns
- `pd.set_option('display.max_rows',85)` - print 85 columns
- `df.head()` - shows first 5 rows
	- `df.head(10)` - shows first 10 rows
- df.tail(10) - shows last 10 items of the data