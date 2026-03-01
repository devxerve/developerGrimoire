---
cssclasses:
  - center-titles
  - center-images
  - rounded-images
  - page-grid
  - pen-red
---

# Jdbc Conexion Java Mysql
Hay que descargarse el .jar de Mysql en su versión “platform independent”
https://dev.mysql.com/downloads/connector/j/

# Ejemplo En Una Clase Separada

```java title="JBDC"
public class BBDD{
    public String url = null;
    public String user= null;
    public String pswd = null;
    public BBDD(){ 
        url = "jdbc:mysql://localhost:3305/centroestudios";
        user= "root";
        pswd = "root";
    }
    static Connection crearConexion(String url, String user, String pswd){
    Connection con1 = null;
    try{
        con1 = DriverManager.getConnection(url, user, pswd);
        if(con1!=null){
            System.out.println("Conexion correcta");
        }
    }catch(SQLException ex){
        ex.printStackTrace();
    }
    return con1;
}
}
```

> [!important]
> PARAMETROS NECESARIOS PARA EL METODO getConnection() de la clase DriverManager
> <sub>(Todo esto teniendo en cuenta que los parámetros pueden tener el nombre que tu quieras)</sub>
> url → indica donde esta nuestra base de datos
> user → Indica el usuario con el cual nos conectamos
> pswd → Indica la contraseña de dicho usuario 

# Ejemplo Conexión

Y podríamos crear una conexión con este método por ejemplo

```java title="Metodo conexion"
    private void btn_conexionActionPerformed(java.awt.event.ActionEvent evt) {                                             
        gestorBBDD = new BBDD();
        Connection con1 = BBDD.crearConexion(gestorBBDD.url,gestorBBDD.user,gestorBBDD.pswd);
        if(con1 !=null){
            textarea1.setText("Conexion correcta a la base de datos");
        }
    }  
```
