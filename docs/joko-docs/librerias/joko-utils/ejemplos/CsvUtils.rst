----------------------------------
CSV (Comma Seperated Values) Utils
----------------------------------
Contiene utilidades para trabajar con el formato CSV.

**Ejemplo del método convertToCsv**:

El metodo transforma una lista de objetos serializables a un texto en formato CSV, devolviendo el resultado como un byte stream.

Inputs:

- List<?> que tendrá objetos de una única clase y que tenga la propiedad de ser serializable.
- List<String> donde cada elemento es ambos la cabecera de una columna del texto CSV así como el nombre del atributo del objeto que ira en las celdas de la columna.
- La clase de los objetos de la List<?> pasada.

Para el ejemplo usaremos la siguiente clase para nuestra lista de objetos, haciendo que sea serializable así como definiendo los Getters para usar los atributos:

.. code-block:: java

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

Generamos los inputs, llamamos al método y escribimos el resultado en un archivo, para utilizar el código de ejemplo debe crear el archivo que contendrá el resultado (Sino dará error) y rellenar el campo "DIRECCION_DEL_ARCHIVO" con la dirección de su archivo:

.. code-block:: java
        
    // Generamos datos del ejemplo
    user1.setName("Miguel");
    user1.setLastName("Leugim");
    user1.setId(12345);

    UserData user2 = new UserData();
    user2.setName("Carlos");
    user2.setLastName("Solrac");
    user2.setId(77777);

    UserData user3 = new UserData();
    user3.setName("Hector");
    user3.setLastName("Rotceh");
    user3.setId(41569);

    List<?> object_list = Arrays.asList(user1, user2, user3);
    List<String> header_list = Arrays.asList("Name", "LastName", "ID");

    // Llamamos al método y guardamos el archivo CSV
    byte [] resultado = CsvUtils.convertToCsv(object_list, header_list, UserData.class);
    FileUtils.writeByteArrayToFile(new File("DIRECCION_DEL_ARCHIVO"), resultado);

El archivo generado por este ejemplo:

.. code-block:: text

    Name,LastName,ID
    "Miguel","Leugim","12345"
    "Carlos","Solrac","77777"
    "Hector","Rotceh","41569"
