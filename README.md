# EXAMEN_WEB

    ///Codigo del archivo MAIN.PY////

from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def inicio():
    return render_template('index.html')


@app.route('/ejercicio1', methods=['GET', 'POST'])
def ejercicio1():
    if request.method == 'POST':
        Ingresatunombre = str(request.form['Ingresatunombre'])
        Ingresatuedad = int(request.form['Ingresatuedad'])
        Ingresalacantidaddetarrosdepinturaacomprar = int(request.form['Ingresalacantidaddetarrosdepinturaacomprar'])
        Ingresatunombre = Ingresatunombre + Ingresatuedad
        Ingresatunombre = Ingresatunombre + Ingresatuedad
        Ingresatunombre = Ingresatunombre * Ingresatuedad
        Ingresatunombre = (Ingresatunombre / Ingresatuedad,1)
        return render_template('ejercicio1.html', Ingresatunombre=Ingresatunombre,Ingresatuedad=Ingresatuedad,Ingresalacantidaddetarrosdepinturaacomprar=Ingresalacantidaddetarrosdepinturaacomprar)

    return render_template('ejercicio1.html')


@app.route('/iniciodesesion', methods=['GET', 'POST'])
def iniciodesesion():
    if request.method == 'POST':
        Ingresatunombre=  str(request.form['Ingresatunombre'])
        Ingresatucontraseña = str(request.form['Ingresatucontraseña'])
        resultado1 = Ingresatunombre + Ingresatunombre
        resultado2 = Ingresatucontraseña + Ingresatucontraseña
        resultado4 = round(Ingresatunombre / Ingresatucontraseña,1)
        return render_template('ejercicio2.html', Ingresatunombre=Ingresatunombre,Ingresatucontraseña=Ingresatucontraseña)

    return render_template('Iniciodesesion.html')


if __name__ == '__main__':
    app.run(debug=True)


    ///SE CREO LA CARPETA TEMPLATES,SE ADJUNTA
     INDEX.HTML

     <!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" type="text/css" href="/static/css/estilosIndex.css">
<!--<link href="{{ url_for('static', filename='css/miestilo.css') }}" rel="stylesheet" type="text/css"> -->

<title>Ejercicios</title>
</head>
<body>
  <div class="button-container">
    <a href="ejercicio1" class="button">Ejercicio1</a>
    <a href="iniciodesesion" class="button">Inicio de Sesion</a>
  </div>
</body>

    ///SE CREA EJERCICIO1.HTML

    <!DOCTYPE html>
<html>
<head>
    <title>Ejercicio 1</title>
    <link rel="stylesheet" type="text/css" href="/static/css/estilosSuma.css">
</head>
<body>
<div class="container">
    <h1>Calculo de Compras</h1>
        <form action="/ejercicio1" method="POST">
        <label for="Ingresatunombre">Ingresa tu nombre:</label>
        <input type="text" id="Ingresatunombre" name="Ingresatunombre" required>
        <br>
        <label for="Ingresatuedad">Ingresa tu edad:</label>
        <input type="number" id="Ingresatuedad" name="Ingresatuedad" required>
        <br>
        <label for="Ingresalacantidaddetarrosdepinturacomprar">Ingresa la cantidad de tarros de pintura a comprar:</label>
        <input type="number" id="Ingresalacantidaddetarrosdepinturacomprar" name="Ingresalacantidaddetarrosdepinturaacomprar" required>
        <br>
        <button type="submit">Enviar</button>
    </form>
    {% if Nota1 and Nota2 and Nota3 and Nota4 %}
    <div> class="resultado">
        <p>Resultado: {{ Ingresatunombre }}</p>
        <h3>El resultado para los numeros {{Ingresatunombre}} y {{Ingresatunombre}}</h3>
        <p>La suma es: {{ Ingresatunombre }}</p>
        <p>La suma es: {{ Ingresatunombre }}</p>
        <p>La suma es: {{ Ingresatunombre }}</p>
        <p>La suma es: {{ Ingresatunombre }}</p>
    </div>
    {% endif %}

</body>
</html>

     ///SE CREA INICIODESESION.HTML

     <!DOCTYPE html>
<html>
<head>
    <title>Inicio de Sesion</title>
    <link rel="stylesheet" type="text/css" href="/static/css/estilosSuma.css">
</head>
<body>
<div class="container">
    <h1>Inicio de Sesion</h1>
    <form action="/iniciodesesion" method="POST">
        <form action="/" method="POST">
        <label for="Ingresatunombre">Ingresa tu nombre:</label>
        <input type="text" id="Ingresatunombre" name="Ingresatunombre" required>
        <br>
        <label for="Ingresatucontraseña">Ingresa tu contraseña :</label>
        <input type="text" id="Ingresatucontraseña" name="Ingresatucontraseña" required>
        <br>
        <button type="submit">Enviar</button>
   </form>
    {% if resultado1 and resultado2 and resultado3 and resultado4 %}
    <div> class="resultado">
        <p>Resultado: {{ resultado }}</p>
        <h3>El resultado para los numeros {{Nota1}} y {{Nota2}}</h3>
        <p>La suma es: {{ resultado1 }}</p>
        <p>La suma es: {{ resultado2 }}</p>
        <p>La suma es: {{ resultado3 }}</p>
        <p>La suma es: {{ resultado4 }}</p>
    </div>
    {% endif %}

</body>
</html>




     ////SE CREA LA CARPETA "STATIC" DONDE SE CREO LA CARPETA CON LA CARPETA "CSS".
     ADJUNTO CODIGO DE "CSS".
      ///ESTILOINDEX.CSS

      body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 20;
    background-color: #f0f0f0;
  }

  .button-container {
    display: grid;
    grid-template-columns: repeat(2, 2fr);
    gap: 30px;

  }


  .button  {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 200px;
    height: 200px;
    font-size: 30px;
    background-color: green;
    color: white;
    border-radius: 0px;
    cursor: pointer;
    transition: background-color 0.2s ease;
  }


  .button:hover {
    background-color: bl;
  }


     ///ESTILONOMBREYEDAD.CSS

     body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

.container {
    max-width: 300px;
    margin: center;
    padding: 80px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.1);
}


h1, h2 {
    text-align: center;
    margin-bottom: 20px;
    color: #333;
}

form {
    text-align: center;
}

label {
    display: block;
    margin-bottom: 5px;
    color: #555;
}

input {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
    border: 1px solid #ccc;
    border-radius: 3px;
}

button {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}


     ////ESTILOSUMA.CSS

     body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

.container {
    max-width: 500px;
    margin: center;
    padding: 100px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.1);
}

.container {
  width: 20em;
  margin-left: auto;
  margin-right: auto;
}


h1 {
    text-align: center;
    margin-bottom: 30px;
    color: #333;
}

form {
    text-align: center;
}

label {
    display: block;
    margin-bottom: 20px;
    color: #333;
}

input {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 1px;
}

button {
    padding: 10px 20px;
    background-color: blue;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}

      
