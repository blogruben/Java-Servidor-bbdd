# Invocar un procedimiento almacenado desde Java

```JDK8
import java.sql.CallableStatement;
import java.sql.Connection;

		try (
			 Connection oConn = Connection connection = DriverManager.getConnection(connectionUrl););
			 CallableStatement procedimientoAlmacenado = oConn.prepareCall( "call nombre_procedimiento (?, ?, ?, ? )" ))
		{
			procedimientoAlmacenado.setString( 1, id );
			procedimientoAlmacenado.setString( 2, aplicacion );
			procedimientoAlmacenado.setInt( 3, estado );
			procedimientoAlmacenado.execute();
			procedimientoAlmacenado.close();
		}
```
