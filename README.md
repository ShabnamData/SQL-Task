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


# df2 = pd.read_sql('Select distinct companyname from dbo.my_table', conn)
# df2

# Valid_customer = [x for x in df['companyname'].dropna().unique()]
# Valid_customer
