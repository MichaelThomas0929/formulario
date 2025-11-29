<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Document</title>
<style>

body{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    flex-direction: column;
}

#form{
    background-color: white;
    width: auto;
    min-width: 250px;
    height: auto;
    min-height: 300px;
    border-radius: 10px;
    margin: 5px;
    box-shadow: 0px 0px 10px black;
    padding: 20px;
    display: none;
}

.form{
    background-color: white;
    width: 250px;
    height: auto;
    min-height: 300px;
    border-radius: 10px;
    margin: 5px;
    box-shadow: 0px 0px 10px black;
    padding: 20px;
    display: block;
}

</style>
</head>
<body>

<button id="botonCrear">Crear caja</button>
<div id="form">
    <p>Titulo</p>
    <input type="text" id="titulo" placeholder="Titulo">

    <p>Descripcion</p>
    <input type="text" id="descripcion" placeholder="Descripcion">

    <p>Comentario</p>
    <input type="text" id="comentario" placeholder="Comentario"><br><br>

    <input type="button" value="Enviar" id="boton">
</div>

</body>

<script>

const botonCrear = document.getElementById("botonCrear");
const form = document.getElementById("form");
let titulo = document.getElementById("titulo");
let descripcion = document.getElementById("descripcion");
let comentario = document.getElementById("comentario");
let boton = document.getElementById("boton");

botonCrear.addEventListener("click", function(){
    form.style.display = "block";
});

boton.addEventListener("click", function(){
    if (titulo.value == "" || descripcion.value == "" || comentario.value == "") {
        alert("Asegurese de rellenar los datos");
    }
    else{
        let elementoForm = document.createElement("div");
        elementoForm.className = "form";
        document.body.appendChild(elementoForm);

        let elementoTitulo = document.createElement("p");
        elementoTitulo.textContent = titulo.value;
        elementoTitulo.style.textAlign = "center";
        elementoForm.appendChild(elementoTitulo);

        let elementoDescripcion = document.createElement("p");
        elementoDescripcion.textContent = "Descripcion: " + descripcion.value;
        elementoForm.appendChild(elementoDescripcion);

        let elementoComentario = document.createElement("p");
        elementoComentario.textContent = "Comentario: " + comentario.value;
        elementoForm.appendChild(elementoComentario);
    }
});

</script>
</html>
