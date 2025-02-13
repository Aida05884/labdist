# Actividad Evaluable 2 - GIT - Control de versiones. DAW Distancia - CIFP Sect. Industrial y Servicios - La Laboral.

> Tarea creada por Aida Montes Cabello para el módulo Despliegue de Aplicaciones Web.

[TOC]

## **Introducción**

En este documento se detallarán los pasos seguidos para la resolución de la Actividad Evaluable 2 de Despliegue de Aplicaciones Web dedicada al uso de GIT. Para ello primero realizaremos el trabajo en un repositorio local mediante la utilización de comandos; después se procederá a trabajar de forma remota con GitHub y la herramienta gráfica Sourcetree;y por último, gestionaremos los conflictos, también con GitHub y Sourcetree.

## **1.** **Trabajo en local**

Antes de comenzar la práctica, escribimos el siguiente comando para que el historial de ramas de Git se mantenga como un árbol:

```
git config --global merge.ff false
```

También hacemos la comprobación pertinente con el código:

```
git config --list
```

<img src="C:/Users/Usuario/AppData/Roaming/Typora/typora-user-images/image-20250211000712495.png" alt="image-20250211000712495"  />

### Ejercicio **1**

Inicializa un nuevo repositorio Git en una carpeta llamada  `"labdist"` y agrega los  archivos proporcionados en el aula virtual. Renombra la rama `master` a `main`, si es necesario. Realiza el primer `commit`. Muestra el log del repositorio.

Para la realización de la primera cuestión, primero accederemos a la carpeta de `labdist` utilizando el código `cd` con la siguiente ruta `/c/Users/Usuario/Desktop/TareaEvaluable2/labdist` que es donde se encuentra dicha carpeta.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211203935123.png" alt="image-20250211203935123" style="zoom: 67%;" />

Una vez dentro, inicializamos el nuevo repositorio Git con el siguiente código:

```
git init
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211204305059.png" alt="image-20250211204305059" style="zoom:67%;" />

Ahora renombraremos la rama `master` a `main` como mostramos a continuación.

```
git branch -M main
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211204632902.png" alt="image-20250211204632902" style="zoom:67%;" />

Vamos a ver el estado de nuestro repositorio mediante:

```
git status
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211210056056.png" alt="image-20250211210056056" style="zoom:67%;" />

Aquí podemos comprobar que tenemos archivos sin seguimiento, por lo que nos sugiere añadirlos mediante:

```
git add .
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211210249334.png" alt="image-20250211210249334" style="zoom:67%;" />

Una vez realizados todos estos cambios, realizaremos el primer `commit` utilizando el código expuesto a continuación.

```
git commit -m "Archivos proporcianados agregados + renombre master a main"
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211210631303.png" alt="image-20250211210631303" style="zoom:67%;" />

Por último, mostramos el log del repositorio.

```
git log
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211210809939.png" alt="image-20250211210809939" style="zoom:67%;" />

### Ejercicio **2**

Incluye un fichero `.gitignore` para que los ficheros `README.md`, `LICENCE.txt` y `passwords.txt` sean ignorados por el control de versiones. Realiza el `commit` y muestra los logs del repositorio en una línea.

Para la creación del ficheros utilizaremos los siguientes códigos para añadirle `README.md`, `LICENCE.txt` y `passwords.txt`

```
echo "README.md" >> .gitignore
echo "LICENCE.txt" >> .gitignore
echo "passwords.txt" >> .gitignore
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211211718403.png" alt="image-20250211211718403" style="zoom:67%;" />

Comprobamos que se ha creado correctamente.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211212445879.png" alt="image-20250211212445879" style="zoom:67%;" />

Una vez comprobado, vamos a añadirlo y crear el segundo commit.

```
git add .
git commit -m "Se ha añadido .gitignore para ignorar ciertos archivos"
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211213311431.png" alt="image-20250211213311431" style="zoom:67%;" />

Por último, mostraremos los logs del repositorio en una línea mediante el comando:

```
git log --oneline
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211213628602.png" alt="image-20250211213628602" style="zoom:67%;" />

### Ejercicio **3**

En el repositorio, crea los archivos `README.md`, `LICENCE.tx`t y `passwords.txt` con algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos ignorados.

Primero, creamos los archivos `README.md`, `LICENCE.tx`t y `passwords.txt` con diferentes contenidos.

```
echo "Contenido de README" > README.md
echo "Contenido de LICENCE" > LICENCE.txt
echo "Contenido de passwords" > passwords.txt
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211214533031.png" alt="image-20250211214533031" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211215110850.png" alt="image-20250211215110850" style="zoom:67%;" />

Mostramos el estado del repositorio.

```
git status
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211215325925.png" alt="image-20250211215325925" style="zoom:67%;" />

Nos muestra que no hay archivos nuevos, ni cambios pendientes y esto es debido a que los archivos creados han sido ignorados, por lo tanto vamos a mostrar a continuación el listado de archivos ignorados.

```
git status --ignored
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211215859367.png" alt="image-20250211215859367" style="zoom:67%;" />

Aquí podemos observar los 3 archivos ignorados.

### Ejercicio **4**

Crea una rama `feature-estilos`. Cámbiate a ella.  

Como bien nos pide el enunciado 4, creamos una rama llamada feature-estilos y nos cambiamos a ella introduciendo el siguiente comando:

```
git checkout -b feature-estilos
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250211235818975.png" alt="image-20250211235818975" style="zoom:67%;" />

- Modifica el archivo  `estilos.css`:  
  - propiedad color del `body` y de propiedad `h2`:  `#2a2a2a` 
  - propiedad `background-color` de `header` y `footer`: `#2a75ff` 
- Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el  mensaje "actualizados estilos a azules".

Una vez modificado el documento `estilos.css` con las propiedades descritas, vamos a ver el estado del repositorio mediante:

```
git status
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212000555219.png" alt="image-20250212000555219" style="zoom:67%;" />

Gracias a la comprobación del estado, podemos ver que se ha modificado el archivo css y que el cambio no están "preparados" para commit, por lo que nos aconseja añadir el cambio para posteriormente realizar el commit.

```
git add .
git commit -m "actualizados estilos a azules"
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212001157497.png" alt="image-20250212001157497" style="zoom:67%;" />

### Ejercicio **5**

Vuelve a la rama `main`. En el archivo `index.html` añade un comentario donde se indique tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje 'añadido autor en index'. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'.

Volvemos a la rama `main` introduciendo el siguiente comando:

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212001532704.png" alt="image-20250212001532704" style="zoom:67%;" />

Para añadir el comentario en el archivo index.html, bien podemos modificarlo directamente abriendo el archivo o bien, introduciendo este código en Git Bash para que añada el comentario con el nombre del autor al final de la página . Nosotros introduciremos el código en Git Bash para hacerlo más rápido y comprobaremos el status del repositorio.

```
echo "<!-- Autor: Aida Montes Cabello -->" >> index.html
git status
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212002739545.png" alt="image-20250212002739545" style="zoom:67%;" />

Como vimos con anterioridad, el status nos muestra como se han realizado cambios y que se necesitan añadir antes de realizar el commit. Para ello realizaremos el add y posteriormente el commit.

```
git add index.html
git commit -m "añadido autor en index"
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212003040206.png" alt="image-20250212003040206" style="zoom:67%;" />

Por último para mostrar los logs del repositorio en una línea (`oneline`), gráficamente (`graph`) y con "decoración" (`decorate`) utilizaremos el siguiente comando:

```
git log --oneline --graph --decorate
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212003400293.png" alt="image-20250212003400293" style="zoom:67%;" />

### Ejercicio **6**

Fusiona la rama `feature-estilos` en la rama `main`. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'.

Para fusionar dicha rama creada con anterioridad en la rama `main` usaremos el código `merge` y posteriormente mostraremos los logs del repositorio como lo hemos hecho en el ejercicio anterior.

```
git merge feature-estilos
git log --oneline --graph --decorate
```

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212010617757.png" alt="image-20250212010617757" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212010742311.png" alt="image-20250212010742311" style="zoom:67%;" />



## **2**. **Trabajo en remoto**

Antes de comenzar a hacer los ejercicios, vamos a comprobar que las opciones de SourceTree sean las correctas. Para ello iremos a `Tools/Options/Git` y que en Push branches esté seleccionada la opción simple.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212103649450.png" alt="image-20250212103649450" style="zoom: 50%;" />

### Ejercicio **1**

Continúa con el repositorio `labdist`. Añade el repositorio a *Sourcetree*.

Para continuar con el repositorio `labdist`, lo añadiremos a Sourcetree.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212104322447.png" alt="image-20250212104322447" style="zoom: 50%;" />

A continuación podemos apreciar como el repositorio se ha añadido correctamente.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212105009990.png" alt="image-20250212105009990"  />

No obstante nos avisaría de una advertencia en la pestaña Remote ya que no hemos configurado el proyecto de forma remota. Más adelante lo añadiremos a GitHub y lo vincularemos.

### Ejercicio **2**

En tu cuenta de GitHub, crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir <u>todas</u> las ramas. Muestra, además, la captura de pantalla donde se vean en GitHub.

Primero de todo, creamos el repositorio remoto con el nombre de labdist para posteriormente subir todas las ramas desde el repositorio local.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212105944468.png" alt="image-20250212105944468" style="zoom:67%;" />



<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212110109938.png" alt="image-20250212110109938" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212110544148.png" alt="image-20250212110544148" style="zoom:67%;" />

Una vez creado, continuamos con la advertencia que nos había salido en el ejercicio 1 que nos avisaba que no había vinculación con un repositorio remoto. Para ello, pulsamos en la advertencia y seguimos los pasos.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212110704044.png" alt="image-20250212110704044" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212111914105.png" alt="image-20250212111914105" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212112149318.png" alt="image-20250212112149318" style="zoom:67%;" />

Una vez añadido, subimos todas las ramas desde `Push`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212112519784.png" alt="image-20250212112519784" style="zoom: 50%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212112622179.png" alt="image-20250212112622179" style="zoom: 50%;" />

Una vez autorizado, ya podemos ver las ramas en nuestro repositorio de GitHub.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212113005416.png" alt="image-20250212113005416" style="zoom:67%;" />

### Ejercicio **3**

En el repositorio <u>local</u>, crea una rama `feature-index`.  Añade el siguiente código dentro de la `<section class="about">`. Añade los cambios y crea un commit con el mensaje "Añadido párrafo equipo en index.html". Sube los cambios al remoto. *(Recuerda que  debes usar SourceTree en todo este apartado).*

```
<h2>Conoce a Nuestro Equipo</h2>
		<p>labdist está formado por un equipo de diseñadores y desarrolladores apasionados que trabajan juntos para ofrecer solucionestecnológicas de alta calidad. Cada miembro de nuestro equipo aporta experiencia en diseño, programación, y soporte técnico, asegurando que nuestros clientes reciban un servicio completo y personalizado.</p>
		<p>Nuestro objetivo es que cada cliente se sienta acompañado en su aventura digital, con un equipo profesional que entiende sus necesidades y trabaja para hacer crecer su presencia en línea.</p>
```

Como bien nos pide el ejercicio, lo primero que haremos será crear una rama llamada `feature-index` en el repositorio local. Para ello pulsamos en la opción Branch para a continuación crear la nueva rama.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212114217993.png" alt="image-20250212114217993" style="zoom: 67%;" />

Ahora ya podemos ver la creación de la rama en nuestro repositorio.

![image-20250212114400640](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212114400640.png)

Una vez creada la rama, procederemos a agregar el código expuesto en el ejercicio  dentro de la `<section class="about">`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212115517284.png" alt="image-20250212115517284" style="zoom:67%;" />

Ahora lo que debemos hacer es añadir los cambios en Sourcetree desde `Stage all`. Para ello pulsamos sobre la notificación que nos dice que hay un archivo pendiente, presionamos sobre `Stage All` y acto seguido, el archivo `index.html` que aparece en `Unstages files` pasa a estar en `Staged files`.

![image-20250212120008529](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212120008529.png)

![image-20250212120517972](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212120517972.png)

Para realizar el commit, utilizaremos el bloque de texto que nos saldrá en la parte inferior de la pantalla.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212120731882.png" alt="image-20250212120731882" style="zoom:67%;" />

A continuación, podremos ver que los cambios se han realizado correctamente.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212120854850.png" alt="image-20250212120854850" style="zoom:67%;" />

Por último, subimos los cambios realizados a remoto como hemos hecho con anterioridad desde la opción `Push`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212121101437.png" alt="image-20250212121101437" style="zoom:67%;" />

Accedemos a GitHub y vemos que nos notifica de ello.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212121406243.png" alt="image-20250212121406243" style="zoom:67%;" />

### Ejercicio **5**

En el repositorio local, fusiona la rama `feature-index` en la rama `main`.

Para fusionar la rama especificada en la rama `main`, lo primero que debemos hacer es posicionarnos en `main`. Para llevarlo a cabo pulsamos con el botón derecho del ratón sobre la rama y seleccionamos `Checkout main...`

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212122909735.png" alt="image-20250212122909735" style="zoom: 67%;" />

Después de cambiarnos de rama, haremos pulsaremos la opción Merge que se encuentra en la parte superior de la pantalla, acto seguido, en la ventana que nos sale, seleccionamos la rama `feature-index` y pulsamos ok.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212123730434.png" alt="image-20250212123730434" style="zoom:67%;" />

Ahora podemos apreciar en Sourcetree como las dos ramas se han fusionado correctamente.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212124128134.png" alt="image-20250212124128134" style="zoom:67%;" />

### Ejercicio **6**

Edita el fichero `contacto.html`. Borra unas líneas. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit.

Para la realización de este ejercicio, hemos borrado la palabra Gijón del pie de página, por lo que Sourtree nos notificará de ello en la pestaña commit, como bien pudimos ver con anterioridad en el ejercicio 3 y seguimos los mismos pasos. En la siguiente captura, a parte de los pasos a seguir, podemos apreciar los cambios realizados en el documento, subrayado en rojo como estaba y subrayado en verde como se ha editado.

![image-20250212125750619](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212125750619.png)

A continuación guardamos el commit correspondiente.

![image-20250212130518046](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212130518046.png)

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212130623824.png" alt="image-20250212130623824" style="zoom:67%;" />

### Ejercicio **7**

Te das cuenta del error. Deshaz TOTALMENTE el commit anterior. Captura el estado actual del repositorio. (*Asegúrate de que el fichero* `contacto.html` *ha recuperado todas  las líneas borradas y no hay cambios pendientes en el repositorio.)*

Para eliminar el commit realizado en el ejercicio anterior,  pulsamos con el botón derecho sobre él y seleccionamos la opción `Reverse commit...`

![image-20250212133444894](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212133444894.png)

Confirmamos que elimine el commit.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212133603204.png" alt="image-20250212133603204" style="zoom:67%;" />

Ahora en Sourcetree podemos ver como el commit se ha invertido, manteniendo todo lo que teníamos con anterioridad.

![image-20250212133743143](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212133743143.png)

Por último, vamos a comprobar que lo que habíamos editado en el archivo `contacto.html` está como estaba al principio y la palabra Gijón sigue escrita.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212132151286.png" alt="image-20250212132151286" style="zoom:67%;" />

### Ejercicio **8**

Crea una rama `feature-mapa` y cámbiate a ella. Incluye este código en el archivo `contacto.html`. Añade los cambios. Realiza un commit. 

```
<section class="map">
		<h2>Nuestra Ubicación</h2>
 		<p>C/Luis Moya 335, Gijón, Asturias</p>
 		<iframe src="https://www.google.com/maps?  q=C%2FLuis%20Moya%20335%2C%20Gij%C3%B3n%2C%20Asturias&output=embed" width="600" height="450" style="border:0;" allowfullscreen=""loading="lazy">
 		</iframe>
</section>
```

Creamos una rama al igual que en el ejercicio 3.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212132922393.png" alt="image-20250212132922393" style="zoom:67%;" />

Como bien nos manda el enunciado, nos cambiamos a la rama creada y lo haremos pulsando con el botón derecho del ratón sobre `feature-mapa` y seleccionando `Checkout feature-mapa`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212184521653.png" alt="image-20250212184521653" style="zoom:67%;" />

Una vez creada la rama y cambiarnos a ella, incluimos el código aportado en el archivo `contacto.html`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212181554462.png" alt="image-20250212181554462" style="zoom:67%;" />

Al incluir el código, en Sourcetree ya nos avisa que se ha realizado algún cambio en algún archivo,  pero antes de ello, vamos a subir nuestro repositorio local a remoto pulsando en `Push` ya que nos avisa de ello.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212190106316.png" alt="image-20250212190106316" style="zoom:67%;" />

Una vez subido, pulsamos en `Commit` donde nos sale el aviso de los cambios y hacemos clic en `Stage All`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212183059787.png" alt="image-20250212183059787" style="zoom:67%;" />

Al añadirlo, ya nos deja realizar el commit pertinente.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212183420705.png" alt="image-20250212183420705" style="zoom:67%;" />

Por último comprobamos a través del gráfico que todo se ha realizado correctamente.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212190358968.png" alt="image-20250212190358968" style="zoom:67%;" />

### Ejercicio **9**

Sube los cambios al remoto - los de todas las ramas. Muestra en el remoto los cambios  del archivo `contacto.html` en la rama `feature-mapa`. 

En el ejercicio anterior, ya habíamos subido cambios a remoto, no obstante volvemos a hacerlo para asegurarnos de ello y que todos los cambios se suban satisfactoriamente. Para ello pulsamos en `Push` y en la ventana que se abre marcamos la opción de seleccionar todo y hacemos clic en `Push` en la parte inferior de la ventana.

![image-20250212191320153](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212191320153.png)

Ahora vamos a mostrar los cambios efectuados en el archivo `contacto.html` en la rama `feature-mapa`. Para poder mostrarlo, tenemos que posicionarnos en la rama `feature-mapa` en nuestro repositorio remoto pulsando sobre el desplegable y seleccionándolo. 

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212192223070.png" alt="image-20250212192223070" style="zoom:67%;" />

Una vez en ella, buscamos el archivo contacto.html y podemos ver el cambio realizado.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212192440254.png" alt="image-20250212192440254" style="zoom:67%;" />

Y por último, si accedemos al commit, podremos ver que cambios se han realizado dentro del propio documento.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212192805609.png" alt="image-20250212192805609" style="zoom:67%;" />

### Ejercicio **10**

En GitHub, en la rama `main`, fusiona la rama `feature-mapa`. Baja los cambios del remoto  a local. Deja los dos repositorios sincronizados. Muestra una captura de pantalla donde  se vea la página principal de tu repositorio remoto.

Lo primero que haremos será fusionar la rama `feature-mapa` en `main` desde GitHub pulsando `Pull resquest`.

![image-20250212194023939](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212194023939.png)

Una vez dentro de esta pestaña, hacemos clic en New pull request.

![image-20250212193916180](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212193916180.png)

Aquí seleccionamos las ramas que queremos fusionar, base la dejamos como está, `base:main` y en compare seleccionamos `feature-maps`.

![image-20250212194445254](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212194445254.png)

Una vez seleccionadas, nos dice que no hay conflictos y se puede hacer la fusión automática.

![image-20250212194246760](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212194246760.png)

Para realizar la fusión creamos una pull request con el nombre Fusión rama reature-mapa en main.

![image-20250212200302232](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212200302232.png)

Ahora nos daría la opción de `Merge pull request` y confirmamos la fusión con `Confirm merge`.

![image-20250212200238169](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212200238169.png)

![image-20250212200410469](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212200410469.png)

Ahora si vamos revisar y confirmar que la fusión se ha hecho de forma satisfactoria, para ello accedemos a `Code` y una vez dentro pulsamos en `Branches`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212201138033.png" alt="image-20250212201138033" style="zoom:67%;" />

![image-20250212200716297](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212200716297.png)

Por último accedemos a nuestro repositorio local y hacemos un Pull.

![image-20250212202024277](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212202024277.png)

## **Conflictos**

### Ejercicio **1**

Crea una rama  `hotfix-js`. Cámbiate a ella. Añade este código en el fichero `script.js`.  Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js".  *(Fíjate en los números de línea de tu editor ...)*

```
if (mensaje.value.trim() === "") { 
		alert("Por favor, ingrese un mensaje."); 
		valid = false; 
	}
```

Primero, creamos la nueva rama y nos cambiamos a ella.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212202539257.png" alt="image-20250212202539257" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212202705288.png" alt="image-20250212202705288" style="zoom:67%;" />

Acto seguido, añadimos el código proporcionado en el fichero `script.js`.

![image-20250212203314954](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212203314954.png)

Confirmamos el cambio en nuestro repositorio y creamos el commit.

![image-20250212203711039](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212203711039.png)

![image-20250212210102492](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212210102492.png)

Por último vemos la creación del commit.

![image-20250212210345752](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212210345752.png)

> [!NOTE]
>
> Antes de realizar el ejercicio 1, realicé el commit del ejercicio 2 con los cambios hechos, por ello y para solventar el error, he revertido el commit que había hecho en main.

### Ejercicio **2**

Vuelve a la rama `main`. En el fichero `script.js` en las mismas líneas que en la cuestión  anterior, añade el código siguiente. Confirma el cambio y haz un commit con el mensaje  "corregido problema en script.js rama main".

```
if (mensaje.value.trim() === "") {
		alert("Ingrese un mensaje, por favor");
		valid = false;
	}
```

Volvemos a posicionarnos en la rama `main` (botón derecho sobre ella y `Checkout main...`)

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212231756917.png" alt="image-20250212231756917" style="zoom:67%;" />

Después de esto, añadimos el código proporcionado en las mismas líneas que en el ejercicio anterior al fichero `script.js`.

Una vez realizados los cambios nos avisa Sourcetree de ello, como hemos podido ver en casos anteriores.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212232557849.png" alt="image-20250212232557849" style="zoom:67%;" />

Añadimos los cambios.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212232850836.png" alt="image-20250212232850836" style="zoom:67%;" />

Y realizamos el commit.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212232928190.png" alt="image-20250212232928190" style="zoom:67%;" />

Así quedaría nuestro gráfico de ramas:

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212233018600.png" alt="image-20250212233018600" style="zoom:67%;" />

### Ejercicio **3**

Fusiona la rama `hotfix-js` en `main`. Debe producirse un conflicto. Resuélvelo como consideres oportuno.  Cuando termines la resolución del conflicto sube los cambios al remoto.

Para fusionar la rama `hotfix-js` en `main` lo primero que tendremos que hacer es comprobar que estamos en la rama `main` y como podemos comprobar en la imagen, estamos en lo correcto. El círculo que sale a la izquierda de la rama quiere decir que estamos posicionados sobre ella.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212233436135.png" alt="image-20250212233436135" style="zoom:67%;" />

Ahora vamos a proceder a la fusión, para ello pulsamos con el botón derecho del ratón sobre la rama `hotfix-js` y seleccionamos la opción de `Merge hotfix-js into current branch`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212233844912.png" alt="image-20250212233844912" style="zoom:67%;" />

Sourcetree nos pregunta que si estamos seguros y le decimos que si. Acto seguido nos sale un mensaje de advertencia en el que nos dice que existe un conflicto y que habría que resolverlo para continuar.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212234117187.png" alt="image-20250212234117187" style="zoom:67%;" />

Una vez que cerramos este mensaje, nos sale en la pantalla lo que mostramos en la imagen siguiente. Lo que debemos hacer es buscar la pestaña conflictos y ahí aparecerán los archivos conflictivos, que en este caso es el mismo archivo que salen en la pestaña de pendientes.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212235101525.png" alt="image-20250212235101525" style="zoom:67%;" />

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212235205209.png" alt="image-20250212235205209" style="zoom:67%;" />

Para resolver el conflicto lo haremos de forma manual abriendo el archivo script.js y viendo como ha aparecido un código un tanto conflictivo.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250212235821478.png" alt="image-20250212235821478" style="zoom:67%;" />

Ajustamos el código eliminando las marcas `<<<<<<<`, `=======`, `>>>>>>>`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250213000100774.png" alt="image-20250213000100774" style="zoom:67%;" />

Una vez guardado el archivo, vamos a Sourcetree y nos situamos encima del archivo, pulsamos el botón derecho y seleccionamos `Resolve Conflicts/Mark Resolved`. Con esto lo que hacemos es marcar el archivo como resuelto.

![image-20250213000448523](Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250213000448523.png)

Y así quedaría nuestro gráfico:

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250213001000251.png" alt="image-20250213001000251" style="zoom:67%;" />

Por último subiremos todos los cambios a remoto. Para ello, como hemos hecho con anterioridad, pulsaremos sobre `Push`, marcaremos la opción de seleccionar todo y clicamos `Push`.

<img src="Actividad%20Evaluable%202%20-%20GIT%20-%20Aida%20Montes%20Cabello.assets/image-20250213001345703.png" alt="image-20250213001345703" style="zoom:67%;" />

## **Subida de documentación**

En la carpeta del proyecto `labdist` creamos una carpeta `docs`. 

Copiamos a esa carpeta el fichero markdown y la carpeta con sus imágenes. Aquí incluiremos también el pdf. 

Añadimos todo al repositorio y lo subimos a remoto.

## **Enlace a mi repositorio**

https://github.com/Aida05884/labdist

## **Enlace a mi videoclip**









