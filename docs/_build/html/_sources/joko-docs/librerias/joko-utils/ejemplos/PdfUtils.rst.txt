-----------
PDF Utils
-----------
Contiene utilidades para trabajar con archivos PDF

**Ejemplo del método pdfGenerator**

El método utiliza los datos pasados para crear un archivo PDF en el directorio especificado con una tabla conteniendo los datos especificados y agregando una firma al final con datos varios incluyendo el nombre de usuario especificado.

Inputs:
data/filename/user
- List<List> con los datos a escribir en la tabla del PDF.
- Un String que contiene el nombre del archivo incluyendo la ruta a este (/home/user/mi_pdf.pdf), el archivo puede o no existir a la hora de correr el método, si se provee Null se creara en el directorio raíz del proyecto.
- Un String con un nombre de usuario que sera incluido en la firma al final del PDF

Generamos los tres inputs para luego llamar al método que escribirá el archivo resultante, debe modificar el campo "DIRECCION_DEL_ARCHIVO" con la dirección de su archivo final (Ej: /home/usuario/Desktop/mi_excel.xls) al igual que el campo "NOMBRE_DE_USUARIO" con un nombre con el cual firmar al final el PDF:

.. code-block:: java

    // Para el ejemplo creamos una lista con los nombres de las columnas y luego una lista por
    // fila
    List<String> cabeceras = Arrays.asList("Nombre Comun", "Nombre Cientifico");
    List<String> L1 = Arrays.asList("Perro", "Canis Lupus Familiaris");
    List<String> L2 = Arrays.asList("Gato", "Felis Silvestris Catus");
    List<String> L3 = Arrays.asList("Conejo", "Oryctolagus Cuniculus");

    // Hacemos la tabla donde cada elemento sera una lista, el orden de las filas sera el orden de
    // las listas, con la primera siendo el nombre de las columnas y el resto registros de la tabla
    List<List> data = Arrays.asList(cabeceras, L1, L2, L3);

    // Definimos el directorio donde se creara el archivo incluyendo su nombre (Terminando en .pdf),
    // si se asigna "null" se utilizara el directorio del proyecto por defecto
    final String fileName = "DIRECCION_DEL_ARCHIVO";

    // Se define un nombre de usuario de modo que se generara una firma al final del PDF
    String user = "NOMBRE_DEL_USUARIO";

    // Al correr el método se creara el archivo y se retornara para ser utilizado
    File resultado = PdfGenerator.fromList(data, fileName, user);

Vista previa del PDF generado por este ejemplo:

.. image:: /_static/images/joko-utils/PdfUtils/pdfGenerator_img1.png
    :align: center
