CsvUtils (CSV - Comma Seperated Values)
---------------------------------------
Contiene utilidades para trabajar con el formato CSV

Ejemplo del método **convertToCsv**:

El metodo transforma una lista de objetos serializables a un texto en formato CSV, devolviendo el resultado como un byte stream.

Inputs:

* Una lista de tipo indefinido que tendrá objetos de una misma clase y cuya clase tenga la propiedad de ser serializable.
* Una lista de Strings donde cada elemento es el nombre de una columna del texto CSV así como el nombre del atributo del objeto cuyo Getter se llamara (Como vera en el ejemplo no es Case-Sensitive).
* La clase de la lista de objetos.

Para el ejemplo usaremos la siguiente clase para nuestra lista de objetos, haciendo que sea serializable así como definiendo los Getters para usar los atributos:

.. code-block:: java
    
    // En nuestra clase  de ejemplo especificamos que es serializable al hacer que implemente 
    // java.io.Serializable pero inclusive sin especificar esto una clase puede ser serializable
    // y utilizarse en el método que sigue
    public class UserData implements java.io.Serializable {
    
        private String name = "NULL";
        private String lastName = "NULL";
        private Integer id = 0;

        public String getName() {
            return name;
        }
        public void setName(String name) {
            this.name = name;
        }

        public String getLastName() {
            return lastName;
        }
        public void setLastName(String lastName) {
            this.lastName = lastName;
        }

        public Integer getId() {
            return id;
        }
        public void setId(Integer id) {
            this.id = id;
        }
    }

Generamos los Objetos en este caso para luego crear las listas, llamar al método y escribir en un archivo el resultado, debe crear el archivo que contendrá el resultado y rellenar el campo "DIRECCION_DEL_ARCHIVO" con la dirección de su archivo

.. code-block:: java
        
    // Creamos 3 objetos de usuarios para nuestro ejemplo
    UserData user1 = new UserData();
    user1.setName("Harken");
    user1.setLastName("Nekrah");
    user1.setId(12345);

    UserData user2 = new UserData();
    user2.setName("Leanne");
    user2.setLastName("Ennael");
    user2.setId(77777);

    UserData user3 = new UserData();
    user3.setName("Hector");
    user3.setLastName("Rotceh");
    user3.setId(41569);

    // Metemos los objetos de usuario en una lista de tipo indefinido
    List<?> object_list = Arrays.asList(user1, user2, user3);
    // Creamos la lista que contiene los nombres de cada columna y cuyos nombres
    // deben coincidir con los atributos de los objetos para que se carguen los 
    // datos correctamente (No es case-sensitive y el orden de la lista se 
    // mantiene en el orden de las columnas del archivo CSV)
    List<String> header_list = Arrays.asList("Name", "LastName", "ID");

    // Llamamos al método con los datos preparados, pasando la lista de objetos,  
    // la lista de cabeceras de columna y la Clase de los Objetos de la primera 
    // lista
    byte [] resultado = CsvUtils.convertToCsv(object_list, header_list, UserData.class);

    // Luego podemos guardar el resultado en un archivo de quererlo
    FileUtils.writeByteArrayToFile(new File("DIRECCION_DEL_ARCHIVO"), resultado);

El archivo generado por este ejemplo:

.. code-block:: text

    Name,LastName,ID
    "Harken","Nekrah","12345"
    "Leanne","Ennael","77777"
    "Hector","Rotceh","41569"
