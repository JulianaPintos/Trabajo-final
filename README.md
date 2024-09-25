

| <img src="caratula.png" alt="Descripción de la imagen" width="60"> | <p align="left"> Base de datos y Gestión de proyecto de software.  <br> TF Base de datos libre. </p>  |
| --------------------------------------- |--------------------------------------------------------------------------------- |


<br>
<p align="center">
  <BR>
   <img src="caratula.png" alt="Carátula del Proyecto" width="200"/><BR>
  <BR>
  <BR>
  <br>
  <BR> Trabajo Final de Base de Datos Libre <BR>
          Elian Cairati ,María Juliana Pintos <BR>
  Técnico Superior en Desarrollo de Software, Escuela Superior de Comercio N° 43<BR>
          3° Base de Datos<BR>
        3° Gestión y Proyectos de Software<BR>
          Ariel Nardelli<BR>
          Matias Nardelli<BR>
        03 de septiembre 2024<BR>
</p> <BR>

<table width="9000%", align="center",long="9000%">
  <tr>
    <td>
       <p align="center",> Elian Cairati, María Juliana Pintos</p>
       <p align="center" >3° Año - Técnico Superior en Desarrollo de Software</p> 
       <p align="center">Escuela Superior de comercio N°43</p>
    </td>
  </tr>
</table>

# Trabajo final
<p alingn="justify">Presentar la base de datos elegida al profesor y realizar un análisis de los archivos excel o del formato que esté la información y en base a eso diseñar una base de datos con sus tablas que contenga dicha información. Diseñar también indices alternativos y las relaciones entre las mismas. <br>Presentar el diseño de las tablas gráficamente mediante el software que usted desee.</p>
<p><b>Lenguaje SQL</b>
<li>Sentencias DDL (Lenguaje de definición de datos) de creación de tablas y relaciones.</li>
<li>Importar los datos desde los archivos excel y llenar las tablas creadas con dicha información.</li></p>
<p>El trabajo debe ser alojado en un repositorio publico en el cual deben estar el archivo de datos publicos utilizado en formato “csv”, un archivo de respaldo de la base de datos una vez finalizada y confeccionar un archivo Readme.md donde describan la base de datos, contener diagrama, y demostración de las sentencias solicitadas anteriormente. Además, crear instrucciones de como importar el archivo de respaldo para ser utilizado por otras personas.</p>

# Introducción
<p aling="justify">En el contexto de elegir una base de datos, el profesor nos proporcionó páginas con bases de datos libres donde podemos buscar la que más nos llame la atención y, al mismo tiempo, cumpla con los requisitos solicitados para el trabajo. En nuestro caso, la base de datos seleccionada gestionará los permisos para eventos masivos del 2024, dado que contiene información sobre los eventos, las localizaciones y las regulaciones implicadas. Se requiere una solución eficiente que permita manejar la información de manera precisa y segura.</p>


# Importar un archivo excel a heidi

Para poder importar una tabla de excel a heidi, demos abrir en heidi y crear una base de datos, una vez que esta creada en la barra de herramientas nos pareca como (importar archivo csv).

<p align="center">
  <img src="p1.png" alt="Primera herramienta como importar archivo csv" width="800"/>
</p>


* Creamos una nueva tabla y colocamos todas las columnas en VARCHAR.
* Determinamos los campos de la forma que es el programa(si es por , o “”).
* En manejo de filas duplicadas colocamos INSERT(puede provocar errores)).
* Ponemos la decodificación en utf8: UTF-8 unicode.

  <div style="display: flex; justify-content: center;">
    <img src="p2.png" alt="Imagen 2" width="300" style="margin: 80px;"/>
    <img src="p3.png" alt="Imagen 3" width="300" style="margin: 80px;"/>
  </div>

# Crear una nueva tabla y exportar la información de forma ordenada
* TABLA 1
<table>
  <tr>
    <td colspan="2">
      <table>
        <tr>
          <p align="center">LUGARES</p>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
           <img src="p4.png" alt="Descripción de la imagen" width="800" long="200">
        </tr>
      </table>
    </td>
    <td>
      <table>
        <tr>
           <p align="left"><li> CREATE TABLE lugares(</li> </p> <p align="left"><li> lug_nuro INT AUTO_INCREMENT NOT NULL PRIMARY KEY,</li></p><p align="left"><li>lug_nomb VARCHAR(120) );</li></p><p align="left">Despues para poder exportar la información de la tabla eventos a lugares decidimos utilizar este comando:></p><p align="left"><li>INSERT INTO lugares (lug_nomb) SELECT distinct(lugar) FROM eventos;</li> </p> 
        </tr>
      </table>
    </td>
  </tr>
</table>
* TABLA 2
<table>
  <tr>
    <td colspan="2">
      <table>
        <tr>
          <p align="center">AFORO</p>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
           <img src="p5.png" alt="Descripción de la imagen" width="800" long="200">
        </tr>
      </table>
    </td>
    <td>
      <table>
        <tr>
           <p align="left"><li> CREATE TABLE aforo(</li> </p> <p align="left"><li> afo_nuro INT AUTO_INCREMENT NOT NULL PRIMARY KEY,</li></p><p align="left"><li>afo_nomb VARCHAR(120));</li></p><p align="left"><li>INSERT INTO aforo (afo_nomb) SELECT distinct(aforo) FROM eventos;</li> </p> 
        </tr>
      </table>
    </td>
  </tr>
</table>
* TABLA 3
<table>
  <tr>
    <td colspan="2">
      <table>
        <tr>
          <p align="center">BARRIOS</p>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
           <img src="p6.png" alt="Descripción de la imagen" width="800" long="200">
        </tr>
      </table>
    </td>
    <td>
      <table>
        <tr>
           <p align="left"><li> CREATE TABLE Barrios(</li> </p> <p align="left"><li> bar_nuro INT AUTO_INCREMENT NOT NULL PRIMARY KEY,</li></p><p align="left"><li>bar_nomb VARCHAR(120) );</li></p><p align="left"><li>INSERT INTO barrios (bar_nomb) SELECT distinct(barrio) FROM eventos;</li> </p> 
        </tr>
      </table>
    </td>
  </tr>
</table>
* TABLA 4
<table>
  <tr>
    <td colspan="2">
      <table>
        <tr>
          <p align="center">EVENTOS_TIPO</p>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
           <img src="p7.png" alt="Descripción de la imagen" width="800" long="200">
        </tr>
      </table>
    </td>
    <td>
      <table>
        <tr>
           <p align="left"><li> CREATE TABLE eventos_tipo(</li> </p> <p align="left"><li> eve_nuro INT AUTO_INCREMENT NOT NULL PRIMARY KEY,</li></p><p align="left"><li>eve_nomb VARCHAR(120) );</li></p><p align="left"><li>INSERT INTO eventos_tipo (eve_nomb) SELECT distinct(evento) FROM eventos;</li> </p> 
        </tr>
      </table>
    </td>
  </tr>
</table>
* TABLA 5
<table>
  <tr>
    <td colspan="2">
      <table>
        <tr>
          <p align="center">MODALIDAD_FORMATO</p>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>
      <table>
        <tr>
           <img src="p8.png" alt="Descripción de la imagen" width="800" long="200">
        </tr>
      </table>
    </td>
    <td>
      <table>
        <tr>
           <p align="left"><li> CREATE TABLE modalidad_formatos(</li> </p> <p align="left"><li> for_nuro INT AUTO_INCREMENT NOT NULL PRIMARY KEY,</li></p><p align="left"><li>for_nomb VARCHAR(120) );</li></p><p align="left"><li>INSERT INTO modalidad_formatos (for_nomb) SELECT distinct(modalidad_formato) FROM eventos;</li> </p> 
        </tr>
      </table>
    </td>
  </tr>
</table>


# Consultas
<p align="justify">Aca dejamos algunas consultas que hicimos a la base de datos:</p><br>
* select fecha as horario,evento ,modalidad_formato as formato, barrio from eventos
where (modalidad_formato = "Recital" or modalidad_formato = "Paseo") and  barrio = "Palermo";<br>

```sql
SELECT  fecha AS horario,modalidad_formato as formato,aforo, barrio, COUNT(*) as evento FROM eventos
WHERE aforo= "990" ;<br>
```

** Esto es un ejemplo **
```sql
select fecha as horario,evento ,modalidad_formato as formato, barrio from eventos
WHERE NOT (modalidad_formato = "Recital" or modalidad_formato = "Paseo");<br>
```
```sql
SELECT fecha AS horario, evento, lugar, modalidad_formato as formato, apertura, cierre,aforo, barrio 
from eventos  WHERE aforo= "990" LIMIT 0,10;<br>
```
```sql
* SELECT fecha AS horario, evento, lugar, modalidad_formato as formato, apertura, cierre,aforo, barrio 
from eventos  WHERE modalidad_formato= "recital" LIMIT 10,10;<br>
```
```sql
select aforo, fecha as horario,evento ,modalidad_formato as formato, barrio from eventos
where (aforo = "1000" or aforo = "5000") or (modalidad_formato = "carrera" or modalidad_formato = "jornada")
ORDER BY modalidad_formato desc , aforo asc;<br>
```

# Sistema de Base de Datos
<p>Para finalizar el trabaja hicimos un diagrama de clases mostrando las relaciones que tienen dichas tablas: </p><br>
<div style="display: flex; justify-content: center;">
    <img src="Base_de_Datos_de_Trabajo.png" width="800" style="margin: 800px;"/>
  </div>
