-----------
PDF Utils
-----------
Contiene utilidades para trabajar con archivos PDF

**Ejemplo del método pdfGenerator**

El método utiliza los datos pasados para crear un archivo PDF en el directorio especificado con una tabla conteniendo los datos especificados y agregando una firma al final con datos varios incluyendo el nombre de usuario especificado.

Inputs:

- List<List> con los datos a escribir en la tabla del PDF.
- Un String que contiene el nombre del archivo incluyendo la ruta a este (/home/user/mi_pdf.pdf), el archivo puede o no existir a la hora de correr el método, si se provee "Null" se creara en el directorio raíz del proyecto.
- Un String con un nombre de usuario que sera incluido en la firma al final del PDF.

Generamos los tres inputs para luego llamar al método que escribirá el archivo resultante, para utilizar el código de ejemplo debe modificar el campo "DIRECCION_DEL_ARCHIVO" con la dirección de su archivo final (Ej: /home/usuario/Desktop/mi_excel.xls) al igual que el campo "NOMBRE_DE_USUARIO" con un nombre con el cual firmar el PDF al final:

.. code-block:: java

    // Generamos datos de prueba
    List<String> cabeceras = Arrays.asList("Nombre Comun", "Nombre Cientifico");
    List<String> L1 = Arrays.asList("Perro", "Canis Lupus Familiaris");
    List<String> L2 = Arrays.asList("Gato", "Felis Silvestris Catus");
    List<String> L3 = Arrays.asList("Conejo", "Oryctolagus Cuniculus");
    List<List> data = Arrays.asList(cabeceras, L1, L2, L3);

    final String fileName = "DIRECCION_DEL_ARCHIVO";

    String user = "NOMBRE_DEL_USUARIO";

    // Creamos el PDF
    File resultado = PdfGenerator.fromList(data, fileName, user);

Vista previa del PDF generado por este ejemplo:

.. image:: /_static/images/joko-utils/PdfUtils/pdfGenerator_img1.png
    :align: center
