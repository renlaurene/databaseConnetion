# databaseConnetion
DatabaseConnection


# Open database connection
db = pymysql.connect("localhost","root","","test" )

# Prepare a cursor object using cursor() method
cursor = db.cursor()

# Prepare SQL query to INSERT a record into the database.
sql = "SELECT * FROM USER" 
try:
   # Execute the SQL command
   cursor.execute(sql)
   # Fetch all the rows in a list of lists.
   results = cursor.fetchall()
   for row in results:
      nm = row[0]
      pwd = row[1]
      # Now print fetched result
      print ("name = %s, password = %s" % \
             (nm, pwd))
except:
   print ("Error: unable to fetch data")

# disconnect from server
db.close()e

