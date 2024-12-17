df = pd.read_csv('proyektm.csv')
df

df.columns( for showing columns)

cursor = conn.cursor()
 cursor.execute('''
     CREATE TABLE Status List (ID int not null identity(1,1),Description varchar(255) not null);
     CREATE TABLE Product Lines(ID int not null identity(1,1),Description varchar(255) not null);
    CREATE TABLE Product Codes (IDint not null identity(1,1),Description varchar(255) not null);)
    )
               
     '''
 )
conn = pyodbc.connect('Driver={SQL Server};'
                        'Server=DESKTOP-NQGB2T3;'
                        'Database=test;'

                        'Trusted_Connection=yes;'
                        "encoding='latin1'")

cursor = conn.cursor()


cursor.execute('''DROP TABLE IF EXISTS StatusList''') 
cursor.execute('''
    CREATE TABLE StatusList (
        ID int not null identity(1,1),
        STATUS varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')
# Create ProductLines table
cursor.execute('''DROP TABLE IF EXISTS ProductLines''')

cursor.execute('''
    CREATE TABLE ProductLines (
        ID int not null identity(1,1),
        PRODUCTLINE varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')
# Create ProductCodes table
cursor.execute('''DROP TABLE IF EXISTS ProductCodes''')

cursor.execute('''
    CREATE TABLE ProductCodes (
        ID int not null identity(1,1),
        PRODUCTCODE varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')
cursor.execute('''DROP TABLE IF EXISTS CustomerNames''')

cursor.execute('''
     CREATE TABLE CustomerNames (
        ID int not null identity(1,1),
        CUSTOMERNAME varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')

cursor.execute('''DROP TABLE IF EXISTS Cities''')
cursor.execute('''
     CREATE TABLE Cities (
        ID int not null identity(1,1),
        CITY varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')

cursor.execute('''DROP TABLE IF EXISTS States''')

cursor.execute(''' 
    CREATE TABLE States (
        ID int not null identity(1,1),
        STATE varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')

cursor.execute('''DROP TABLE IF EXISTS PostalCodes''')

cursor.execute(''' 
    CREATE TABLE PostalCodes (
        ID int not null identity(1,1),
        POSTALCODE varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')

cursor.execute('''DROP TABLE IF EXISTS Countries''')

cursor.execute(''' 
    CREATE TABLE Countries (
        ID int not null identity(1,1),
        COUNTRY varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')

cursor.execute('''DROP TABLE IF EXISTS DealSizeList''')
cursor.execute('''
     CREATE TABLE DealSizeList (
        ID int not null identity(1,1),
        DEALSIZE varchar(255) not null,
        PRIMARY KEY (ID)
    )
''')
# cursor.execute('''DROP TABLE IF EXISTS Fact_df_KPI''')

# cursor.execute('''
#      CREATE TABLE Fact_df_KPI (
#         KPI_ID int not null identity(1,1),
#         ORDERNUMBER	int not null indentity(1,1)
#         QUANTITYORDERED int not null indentity(1,1)
#         PRICEEACH int not null indendity(1,1)
#         ORDERLINENUMBER int not null indentity(1,1)
#         SALES int not null indentity(1,1)
#         ORDERDATE int not null indentity(1,1)
#         STATUS str not null indentity(1,1)
#         QTR_ID	int not null indentity(1,1)
#         MONTH_ID  int not null indentity(1,1)
#         YEAR_ID int not null indentity(1,1)
#         ADDRESSLINE1 int not null indentity(1,1)
#         ADDRESSLINE2 str not null identity(1,1)
                                    
#         PRIMARY KEY (ID)
#     )
               
# ''')
# Commit the changes
conn.commit()

# Close the cursor and the connection
cursor.close()
conn.close()     

# result = cursor.fetchall()

# df = pd.read_sql('Select * from dbo.Customers', conn)
# df
# cursor.close()
# conn.close
# df

# def create_tables_and_insert_data(table_name, column_name, values):
#     conn = sqlite3.connect('dimension_tables.db')
#     c = conn.cursor()
#     c.execute(f"CREATE TABLE {table_name} (ID INTEGER PRIMARY KEY AU[TOINCREMENT, Description TEXT)")
#     for value in values:
#         c.execute(f"INSERT INTO {table_name} (Description) VALUES (?)", (value,))
#     conn.commit()
#     conn.close()
# Initialize empty dictionaries for each field
# StatusList = {}
# ProductLines = {}
# ProductCodes= {}
# CostumerNames = {}
# Cities = {}
# States = {}
# PostalCodes = {}
# Countries = {}
# DealSizeList = {}

# # Iterate over the data and populate the dictionaries with unique values
# for index, row in df.iterrows():
#     StatusList [row['StatusList']] = True
#     ProductLines[row['ProductLines']] = True
#     ProductCodes[row['ProductCodes']] = True
#     CostumerNames[row['CustomerNames']] = True
#     Cities[row['Cities']] = True
#     States[row['States']] = True
#     PostalCodes[row['PostalCodes']] = True
#     Countries[row['Countries']] = True
#     DealSizeList[row['DealSizeList']] = True

# status_table = pd.DataFrame({'ID': range(1, len(StatusList ) + 1),
#                             'Description': list(StatusList .keys())})


# df2 = pd.read_sql('Select distinct companyname from dbo.my_table', conn)
# df2

# product_lines_table = pd.DataFrame({'ID': range(1, len(ProductLines) + 1),
#                                     'Description': list(ProductLines.keys())})

# product_codes_table = pd.DataFrame({'ID': range(1, len(ProductCodes) + 1),
#                                     'Description': list(ProductCodes.keys())})

# customer_names_table = pd.DataFrame({'ID': range(1, len(CostumerNames) + 1),
#                                      'Description': list(CostumerNames.keys())})

# cities_table = pd.DataFrame({'ID': range(1, len(Cities) + 1),
#                              'Description': list(Cities.keys())})

# states_table = pd.DataFrame({'ID': range(1, len(States) + 1),
#                              'Description': list(States.keys())})

# postal_codes_table = pd.DataFrame({'ID': range(1, len(PostalCodes) + 1),
#                                    'Description': list(PostalCodes.keys())})

# countries_table = pd.DataFrame({'ID': range(1, len(Countries) + 1),
#                                 'Description': list(Countries.keys())})

# deal_size_list_table = pd.DataFrame({'ID': range(1, len(DealSizeList) + 1),
#                                      'Description': list(DealSizeList.keys())})
# Valid_customer = [x for x in df['companyname'].dropna().unique()]
# Valid_customer
# Valid_customer = [x for x in df[['StatusList','Productlines','ProductCodes','CustomerNames','Cities','States','PostalCodes','Countries','DealSizeList']].dropna()]
# Valid_customer
# cursor = conn.cursor()
# for index, row in df.iterrows():
#     cursor.execute('INSERT INTO [test].[Fact_df_KPI] (StatusList,Productlines,ProductCodes,CustomerNames,Cities,States,PostalCodes,Countries,DealSizeList) VALUES (?, ?, ?, ?, ?, ?, ?, ?)',
#                    row['StatusList'], row['Productlines'], row['ProductCodes'], row['CustomerNames'], row['Cities'], row['States'], row['PostalCodes'], row['Countries'],row['DealSizeList'])
# conn.commit()

# # df.to_excel('test.xlsx')


# conn.close()
df.drop_duplicates(inplace=True)
df
Unique_status = [x for x in df['STATUS'].dropna().unique()]
Unique_PRODUCTLINE = [x for x in df['PRODUCTLINE'].dropna().unique()]
Unique_CUSTOMERNAME = [x for x in df['CUSTOMERNAME'].dropna().unique()]
Unique_CITY = [x for x in df['CITY'].dropna().unique()]
Unique_STATE = [x for x in df['STATE'].dropna().unique()]
Unique_POSTALCODE = [x for x in df['POSTALCODE'].dropna().unique()]
Unique_COUNTRY = [x for x in df['COUNTRY'].dropna().unique()]
Unique_DEALSIZE = [x for x in df['DEALSIZE'].dropna().unique()]
import pyodbc
conn = pyodbc.connect('Driver={SQL Server};'
                      'Server=DESKTOP-NQGB2T3;'
                      'Database=test;'
                      'Trusted_Connection=yes;')
cursor = conn.cursor()
for i in Unique_status:
   cursor.execute("INSERT INTO [dbo].[StatusList] (STATUS) values(?)", (i,))
conn.commit() 
for i in Unique_PRODUCTLINE:
 cursor.execute("INSERT INTO [dbo].[PRODUCTLINES] (PRODUCTLINE) values(?)", (i,))
conn.commit()
for i in Unique_CUSTOMERNAME:
    cursor.execute("INSERT INTO [dbo].[CustomerNames] (CUSTOMERNAME) values(?)", (i,))
conn.commit()
for i in Unique_CITY:
    cursor.execute("INSERT INTO [dbo].[Cities] (CITY) values(?)", (i,))
conn.commit()
for i in Unique_STATE:
    cursor.execute("INSERT INTO [dbo].[States] (STATE) values(?)", (i,))
conn.commit()
for i in Unique_POSTALCODE:
    cursor.execute("INSERT INTO [dbo].[PostalCodes] (POSTALCODE) values(?)", (i,))
conn.commit()
for i in Unique_COUNTRY:
    cursor.execute("INSERT INTO [dbo].[Countries] (COUNTRY) values(?)", (i,))
    conn.commit()
for i in Unique_DEALSIZE:
    cursor.execute("INSERT INTO [dbo].[DealSizeList] (DEALSIZE) values(?)", (i,))
conn.commit() 

cursor.close()
conn.close ()


conn = pyodbc.connect('Driver={SQL Server};'
                        'Server=DESKTOP-NQGB2T3;'
                        'Database=test;'

                        'Trusted_Connection=yes;'
                        "encoding='latin1'")

StatusList = pd.read_sql('Select * from dbo.StatusList', conn)
Productlines = pd.read_sql('Select * from dbo.Productlines', conn)
CustomerNames=pd.read_sql('Select * from dbo.CustomerNames', conn)
Cities = pd.read_sql('Select * from dbo.Cities', conn)
States = pd.read_sql('Select * from dbo.States', conn)
Countries = pd.read_sql('Select * from dbo.Countries', conn)
DealSizeList = pd.read_sql('Select * from dbo.DealSizeList', conn)
PostalCodes = pd.read_sql('Select * from dbo. PostalCodes', conn)

conn.close () 
merged=pd.merge(df,StatusList, left_on='STATUS',right_on='STATUS',how='inner')
merged=pd.merge(merged,Productlines, left_on='PRODUCTLINE',right_on='PRODUCTLINE',how='inner')
merged=pd.merge(df,CustomerNames, left_on='CUSTOMERNAME',right_on='CUSTOMERNAME',how='inner')
merged=pd.merge(df,Cities, left_on='CITY',right_on='CITY',how='inner')
merged=pd.merge(df,States, left_on='STATE',right_on='STATE',how='inner')
merged=pd.merge(df,Countries, left_on='COUNTRY',right_on='COUNTRY',how='inner')
merged=pd.merge(df,PostalCodes, left_on='POSTALCODE',right_on='POSTALCODE',how='inner')
merged=pd.merge(df,DealSizeList, left_on='DEALSIZE',right_on='DEALSIZE',how='inner')
