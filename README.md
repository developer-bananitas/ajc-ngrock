# ajc-ngrock
# TUTORIAL CREACION SERVIDOR EN NODE.JS LIVERELOAD CON SU RESPECTIVA PUBLICACION EN NGROK
##               POR FAVOR SIGAN LOS PASOS BIEN QUE LES DIRE A CONTINUACION
### PROGRAMAS NECESARIOS:  
#### Ojo antes de continuar con los siguientes pasos deben tener una cuenta creada en "GiHub"  
* Tener instalado GitBash link de descarga https://git-for-windows.github.io/  
* Tener instalado GitHub link de descarga https://desktop.github.com/  
* Tener instalado ngrok link de descarga https://ngrok.com/download  
* Tener instalado node.js link descarga https://nodejs.org/es/
* Tener instalado el editor de codigo de preferecia  
**PASOS A SEGUIR:**  
**PASO-1:**  
: crean una carpeta donde va estar todos sus proyectos ejemplo(C:\proyectos)  
**PASO-2:**  
: abren el programa GitHub inician sesion con su respectivo username and password  
**PASO-3:**  
: una vez abierto el programa se dirigen a la opcion File click en la opcion New repository y les abrira una pequeña ventana emergente con las siguientes opciones  
**PASO-4:**  
: en la ventana emergente les pedira Name el nombre del proyecto que van a crear ejemplo(ajc-ngrok)  
: tambien les pedira Local path y dan click en el boton Choose y seleccionan la carpeta que crearon en el PASO-1  
: luego marcan la opcion que dice initialize this repository with a README  
: las demas dos opciones dejenlo en None  
: por ultimo click Create repository  
**PASO-5**      
: ubicarnos en la carpeta creada ejemplo(C:\proyectos\ajc-ngrock)  
: click derecho sobre la carpeta ir a la opcion Git Bash Here  
: se les abrira la respectiva terminal en GitBash  
**PASO-6**  
: ejecutan la linea de comando **npm init** (lo demas ya saben)  
: a continuacion ejecutan el siguiente comando **npm install http --save** esperan que termine la instalacion  
: luego ejecutan **npm install node-static --save** esperan que termine la instalacion  
: y despues ejecutan **npm install livereload --save** esperan que ternime la instalacion  
**PASO-7**  
: crean una carpeta llamada **public**  
: luego crean un archivo **server.js** en la raiz del proyecto(ajc-ngrok)  
: luego ponen el siguiente codigo  
~~~
var nodestatic = require('node-static'),
    port = 3030,
    http = require ('http');

var file = new nodestatic.Server('./public',{
    cache:3600,
    gzip:true
});

http.createServer(function(request,response){
    request.addListener('end',function(){
        file.serve(request,response);
    }).resume();
}).listen(port);

var livereaload=require('livereload');
var server = livereaload.createServer({
    exts:['html','css','js']
});

server.watch(__dirname+"/public");

console.log("Servidor corriendo puerto" + port);
~~~
**PASO-8**  
: dentro de la carpeta **public** crean un archivo llamado **index.html**  
: dentro del archivo **html** escriben la estructura basica de un documento **html**  
**PASO-9**  
: luego en la terminal ejecutan la liena de comando **node server.js**  
: y se levantara el servidor en el puerto **3030**  
**PASO-10**  
: ahora abrimos el programa **ngrok.exe**  
: luego escribimos **ngrok.exe http 3030**  
: luego copias el enlace que te genera en la variable **Forwarding** cualquiera de los dos  
![Sin titulo](img/sonsosgg.png)  
: si no pueden hacer esto contactarme al celular **68695459** preguntar por **BANANITAS**
