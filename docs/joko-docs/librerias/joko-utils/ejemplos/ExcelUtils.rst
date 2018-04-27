-----------
Excel Utils
-----------
Contiene utilidades para trabajar con archivos Excel.

**Ejemplo del método generateExcel**

El método utiliza los datos pasados para crear un archivo Excel en el directorio especificado con los datos especificados.

Inputs:

- Table<Integer, Integer, Object> donde los Integer especifican la celda del archivo Excel y el Object contiene el dato a escribir en la celda (Utiliza la cabecera de la columna para saber que atributo leer del Object).
- List<String> que contiene las cabeceras de la tabla.
- String que contiene el nombre del archivo incluyendo la ruta a este (/home/user/mi_excel.xls), el archivo puede o no existir a la hora de correr el método.

Generamos los tres inputs para luego llamar al método que creara el archivo resultante, para utilizar el ejemplo debe modificar el campo "DIRECCION_DEL_ARCHIVO" con la dirección de su archivo (Ej: /home/usuario/Desktop/mi_excel.xls):

.. code-block:: java

    // Generamos datos para el ejemplo 
    final String fileName = "DIRECCION_DEL_ARCHIVO";

    List<String> header = Arrays.asList("Name", "LastName", "Email", "Cellphone");

    Table<Integer, Integer, Object> data = HashBasedTable.create();
    for (int i = 0; i < 10; i++) {
        data.put(i, 0, "Joko " + i);
        data.put(i, 1, "Utils " + i);
        data.put(i, 2, "jokoutils" + i + "@gmail.com");
        data.put(i, 3, 123456*i);
    }

    // Creamos el archivo Excel
    ExcelUtils excelGenerator = new ExcelUtils();
    excelGenerator.generateExcel(data, header, fileName);

Vista previa del archivo generado por este ejemplo:

.. image:: /_static/images/joko-utils/ExcelUtils/generateExcel_img1.png
    :align: center
