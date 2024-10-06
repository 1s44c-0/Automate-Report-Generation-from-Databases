import sqlite3
import pandas as pd

def generate_report(db_path, query, output_file):
    # Connect to the database
    conn = sqlite3.connect(db_path)
    
    # Execute the query and load data into a DataFrame
    df = pd.read_sql_query(query, conn)
    
    # Perform any data manipulation or analysis here
    # Example: Add a new column with calculated values
    df['Total'] = df['Quantity'] * df['Price']
    
    # Save the DataFrame to Excel
    df.to_excel(output_file, index=False)
    
    print(f"Report generated and saved to {output_file}")
    conn.close()

if __name__ == "__main__":
    db_path = "business.db"
    query = "SELECT item, quantity, price FROM sales"
    output_file = "sales_report.xlsx"
    generate_report(db_path, query, output_file)
