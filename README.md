# Database-Program

package raj;
import  java.sql.*;

public class database {
	
	public static void main(String[] args) throws SQLException {
	//console.log('rajesh edited this');
	//console.log('rajesh edited this');
		ResultSet rs= null;
		Statement stmt=null;
		Connection conn=null;
		try {
			Class.forName("com.mysql.jdbc.Driver");
		
			conn=DriverManager.getConnection("jdbc:mysql://localhost:3306/test","root","test");
			
			stmt=conn.createStatement();
			
			rs=stmt.executeQuery("select * from studaddr");
			
			while(rs.next()){
				System.out.println(rs.getInt("addrnum"));
				System.out.println(rs.getString("addr")):
				//System.out.println(rs.getString("email"));
				 
			}
			
		} catch (ClassNotFoundException e) {
			e.printStackTrace();
		}
		finally
		{
			rs.close();
		      stmt.close();
		      conn.close();
		}
		

	}

}


