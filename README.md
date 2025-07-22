# Data-Analytics---SQL-Python

1. Read file -> data = pd.read_excel(r"..\.xlsx")
2. Drop fields -> data = data.drop(columns = 'col_name')
3. Metadata
   -> data.info() - will show the list of **non-null values count for corresponding fields w/ dtype**
   -> data.describe() - will show the count of records.
   
5. Cleaning
   -> print(data.isnull().sum()) # show the **count of null/empty values** in a field. <checking missing values - null, empty spaces>
   -> data_cleaned = data.dropna() # Drop rows with any missing values

   -> print(data.duplicated().sum())  # Check duplicate rows
   -> data = data.drop_duplicates()    # Drop duplicates
   
7. Cleaning Column
   -> data['Age'] = data['Age'].astype(int)   # **Convert column to integer (if no missing values)**
   -> data.rename(columns={'Name': 'FullName', 'Age': 'AgeYears'}, inplace=True)  # **rename**
   -> data['col_name'] = data['col_name'].str.strip("<menton any symbols ar any to remove from the columns values>")  #../
   -> data['Name'] = data['Name'].fillna('Unknown') # **Fill missing values** with a placeholder
   -> data['Age'] = data['Age'].fillna(data['Age'].mean())  # **Fill missing numeric values** with the mean
   -> data['Phone_Number'].str.replace('[^a-z,A-A,0-9]','')
   -> data['Phone_Number'] = data['Phone_Number'].apply(lambda x: str(x)) # loop or lambda
   -> data['Phone_Number'] = data['Phone_Number'].apply(lambda x: x[0:3] + '-' + x[3:6]+ '-' + x[6:10])
   -> data['Phone_Number'] = data['Phone_Number'].str.replace('nan--','')
   -> data[["Street_Address", "State", "Zip_COde"]] = data['Address'].str.split(',',2, expand=True)  => "980 Paper Avenue, Pennsylvania, 18503"
   -> data = data.replace('N/a', '')
   -> data = data.fillna('')   #remove NaN by empty
   -> Function:
              for x in data.index:
                if data.loc[x, "Do_Not_Contact"] == 'Y': 
                  data.drop(x, inplace=True)
              data

   -> data = data.reset_index(drop=True)
   -> df['arrival_date'] = df['arrival_date_month'].astype(str) + '-' + df['arrival_date_year'].astype(str)
   
    
   
