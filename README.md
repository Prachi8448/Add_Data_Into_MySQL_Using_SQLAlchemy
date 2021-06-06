# Add_Data_Into_MySQL_Using_SQLAlchemy



from sqlalchemy import create_engine

my_conn = create_engine("mysql+mysqldb://userid:password@localhost/database_name")

try:
    query="INSERT INTO  `database_name`.`student` (`name` ,`class` ,`mark` ,`sex`)  VALUES(%s,%s,%s,%s)"
    
    my_data=[('Prachi','B.Tech',82,'Female'),
    
            ('Akansha','B.Tech',88,'Female')]
            

    id=my_conn.execute(query,my_data)
    
    print("Rows Added  = ",id.rowcount)
    
except:

    print("Database error ")
