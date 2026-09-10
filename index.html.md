```html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RPG Card Game</title>

<style>

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    background: #101217;
    color: white;
}

/* =========================
   HEADER
========================= */

header {
    text-align: center;
    padding: 25px;
    background: #181b22;
    border-bottom: 1px solid #30343d;
}

header h1 {
    margin: 0;
}

header p {
    color: #9da3ad;
}

/* =========================
   CONTENEDOR
========================= */

main {
    width: min(1100px, 94%);
    margin: 25px auto;
}

/* =========================
   PANELES
========================= */

.panel {
    background: #181b22;
    border: 1px solid #30343d;
    border-radius: 14px;
    padding: 25px;
    margin-bottom: 20px;
}

.panel h2 {
    margin-top: 0;
}

/* =========================
   PERSONAJE
========================= */

.name-input {
    width: 100%;
    padding: 12px;
    background: #101217;
    border: 1px solid #444954;
    border-radius: 8px;
    color: white;
    font-size: 16px;
    margin-bottom: 20px;
}

.stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
}

.stat {
    background: #22262e;
    border-radius: 12px;
    padding: 20px;
    text-align: center;
}

.stat.red {
    border-top: 4px solid #e74c3c;
}

.stat.green {
    border-top: 4px solid #2ecc71;
}

.stat.blue {
    border-top: 4px solid #3498db;
}

.stat-icon {
    font-size: 35px;
}

.stat-name {
    font-weight: bold;
    margin: 10px 0;
}

.stat input {
    width: 80px;
    padding: 10px;
    background: #101217;
    border: 1px solid #444954;
    border-radius: 8px;
    color: white;
    text-align: center;
    font-size: 18px;
}

.total {
    text-align: center;
    font-size: 20px;
    margin: 20px;
}

/* =========================
   BOTONES
========================= */

.buttons {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
}

button {
    padding: 12px 18px;
    border: none;
    border-radius: 8px;
    background: #5865f2;
    color: white;
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    filter: brightness(1.15);
}

button.secondary {
    background: #30343d;
}

button.danger {
    background: #b83b3b;
}

button.warning {
    background: #8c6418;
}

/* =========================
   INFORMACIÓN
========================= */

.info {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 20px;
}

.info-box {
    background: #181b22;
    border: 1px solid #30343d;
    border-radius: 12px;
    padding: 18px;
    text-align: center;
}

.info-box strong {
    display: block;
    font-size: 25px;
    margin-top: 5px;
}

/* =========================
   JUEGO
========================= */

.game {
    background: #181b22;
    border: 1px solid #30343d;
    border-radius: 14px;
    padding: 25px;
}

.game-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 15px;
}

.game-header h2 {
    margin: 0;
}

.turn {
    color: #9298a3;
    margin-top: 5px;
}

/* =========================
   MAZO
========================= */

.deck-area {
    display: flex;
    justify-content: center;
    margin: 30px;
}

.deck {
    width: 130px;
    height: 180px;
    border-radius: 14px;

    background:
        repeating-linear-gradient(
            45deg,
            #303641,
            #303641 8px,
            #242933 8px,
            #242933 16px
        );

    border: 3px solid #666d7b;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    box-shadow: 0 10px 25px rgba(0,0,0,.5);
}

.deck-icon {
    font-size: 40px;
}

.deck-number {
    font-size: 25px;
    font-weight: bold;
}

/* =========================
   CONTROLES DE ROBO
========================= */

.draw-controls {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 20px;
}

.draw-controls label {
    color: #bfc3ca;
}

.draw-controls input {
    width: 70px;
    padding: 11px;
    background: #101217;
    border: 1px solid #444954;
    border-radius: 8px;
    color: white;
    text-align: center;
    font-size: 16px;
}

/* =========================
   MANO
========================= */

.section-title {
    text-align: center;
    color: #c7cbd3;
}

.hand {
    min-height: 210px;

    background: #101217;
    border-radius: 12px;

    padding: 20px;

    display: flex;
    justify-content: center;
    align-items: flex-end;

    gap: 12px;
    flex-wrap: wrap;
}

/* =========================
   CARTAS
========================= */

.card {
    width: 125px;
    height: 175px;

    background: #252a33;

    border: 4px solid #555b68;

    border-radius: 13px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;

    padding: 12px;

    cursor: pointer;

    transition: .2s;

    user-select: none;
}

.card:hover {
    transform: translateY(-10px);
}

.card.selected {
    transform: translateY(-25px);

    box-shadow:
        0 0 0 3px white,
        0 15px 25px rgba(0,0,0,.5);
}

.card.red {
    border-color: #e74c3c;
}

.card.green {
    border-color: #2ecc71;
}

.card.blue {
    border-color: #3498db;
}

.card-symbol {
    font-size: 45px;
    text-align: center;
}

.card-name {
    text-align: center;
    font-weight: bold;
}

.card-number {
    text-align: center;
    color: #888f9b;
    font-size: 11px;
}

/* =========================
   DESCARTE
========================= */

.discard {
    min-height: 140px;

    background: #101217;

    border-radius: 12px;

    padding: 20px;

    display: flex;
    justify-content: center;

    gap: 10px;
    flex-wrap: wrap;
}

.discard .card {
    width: 85px;
    height: 120px;

    padding: 7px;

    cursor: default;
}

.discard .card:hover {
    transform: none;
}

.discard .card-symbol {
    font-size: 28px;
}

/* =========================
   MENSAJE VACÍO
========================= */

.empty {
    width: 100%;
    text-align: center;
    color: #666c77;
    padding: 50px 10px;
}

/* =========================
   RESPONSIVE
========================= */

@media(max-width:700px) {

    .stats {
        grid-template-columns: 1fr;
    }

    .info {
        grid-template-columns: repeat(2, 1fr);
    }

    .card {
        width: 100px;
        height: 145px;
    }

}

</style>
</head>


<body>

<header>

    <h1>RPG Card Game</h1>

    <p>
        Prototipo de sistema de cartas
    </p>

</header>


<main>


<!-- ===================================
     CREACIÓN DEL PERSONAJE
==================================== -->

<section class="panel">

    <h2>Personaje</h2>

    <input
        id="characterName"
        class="name-input"
        type="text"
        value="Mi Personaje"
        placeholder="Nombre del personaje"
    >


    <div class="stats">


        <!-- ROJO -->

        <div class="stat red">

            <div class="stat-icon">
                🔴
            </div>

            <div class="stat-name">
                Resistencia
            </div>

            <input
                id="redStat"
                type="number"
                min="0"
                value="12"
            >

        </div>


        <!-- VERDE -->

        <div class="stat green">

            <div class="stat-icon">
                🟢
            </div>

            <div class="stat-name">
                Destreza
            </div>

            <input
                id="greenStat"
                type="number"
                min="0"
                value="6"
            >

        </div>


        <!-- AZUL -->

        <div class="stat blue">

            <div class="stat-icon">
                🔵
            </div>

            <div class="stat-name">
                Inteligencia
            </div>

            <input
                id="blueStat"
                type="number"
                min="0"
                value="3"
            >

        </div>

    </div>


    <div class="total">

        Total del mazo:

        <strong id="total">
            21
        </strong>

        cartas

    </div>


    <div class="buttons">

        <button onclick="crearMazo()">
            Crear / Actualizar Mazo
        </button>

        <button
            class="secondary"
            onclick="guardar()"
        >
            Guardar
        </button>

        <button
            class="secondary"
            onclick="cargar()"
        >
            Cargar
        </button>

    </div>

</section>



<!-- ===================================
     INFORMACIÓN DEL MAZO
==================================== -->

<section class="info">

    <div class="info-box">

        🔴 Resistencia

        <strong id="infoRed">
            12
        </strong>

    </div>


    <div class="info-box">

        🟢 Destreza

        <strong id="infoGreen">
            6
        </strong>

    </div>


    <div class="info-box">

        🔵 Inteligencia

        <strong id="infoBlue">
            3
        </strong>

    </div>


    <div class="info-box">

        🃏 Mazo

        <strong id="deckCount">
            21
        </strong>

    </div>

</section>



<!-- ===================================
     MESA
==================================== -->

<section class="game">


    <div class="game-header">

        <div>

            <h2 id="playerName">
                Mi Personaje
            </h2>

            <div class="turn">

                Turno:
                <span id="turn">
                    1
                </span>

            </div>

        </div>


        <div class="buttons">

            <button onclick="robarUna()">
                Robar 1
            </button>

            <button onclick="nuevoTurno()">
                Nuevo turno
            </button>

        </div>

    </div>



    <!-- ===================================
         MAZO
    ==================================== -->

    <div class="deck-area">

        <div class="deck">

            <div class="deck-icon">
                🂠
            </div>

            <div class="deck-number" id="deckBig">
                21
            </div>

            <small>
                cartas
            </small>

        </div>

    </div>



    <!-- ===================================
         CONTROLES DE ROBO
    ==================================== -->

    <div class="draw-controls">

        <label for="drawAmount">
            Cartas a robar:
        </label>

        <input
            id="drawAmount"
            type="number"
            min="1"
            value="5"
        >

        <button onclick="robarMano()">
            Robar mano
        </button>

        <button
            class="secondary"
            onclick="barajarMazo()"
        >
            Barajar mazo
        </button>

    </div>



    <!-- ===================================
         MANO
    ==================================== -->

    <h3 class="section-title">
        Tu mano
    </h3>


    <div
        id="hand"
        class="hand"
    >

        <div class="empty">

            Roba cartas para comenzar.

        </div>

    </div>


    <div
        class="buttons"
        style="margin-top:20px;"
    >

        <button onclick="usarSeleccionadas()">
            Usar cartas
        </button>

        <button
            class="secondary"
            onclick="descartarSeleccionadas()"
        >
            Descartar
        </button>

    </div>



    <!-- ===================================
         DESCARTE
    ==================================== -->

    <h3 class="section-title">
        Descarte
    </h3>


    <div
        id="discard"
        class="discard"
    >

        <div class="empty">

            No hay cartas descartadas.

        </div>

    </div>


    <div
        class="buttons"
        style="margin-top:20px;"
    >

        <button
            class="warning"
            onclick="devolverDescarte()"
        >
            ↩ Devolver descarte al mazo
        </button>

    </div>


</section>

</main>



<script>

/* =================================================
   VARIABLES DEL JUEGO
================================================= */

let mazo = [];

let mano = [];

let descarte = [];

let turno = 1;

let siguienteID = 1;


/* =================================================
   INFORMACIÓN DE LOS COLORES
================================================= */

const colores = {

    rojo: {
        nombre: "Resistencia",
        simbolo: "🔴",
        clase: "red"
    },

    verde: {
        nombre: "Destreza",
        simbolo: "🟢",
        clase: "green"
    },

    azul: {
        nombre: "Inteligencia",
        simbolo: "🔵",
        clase: "blue"
    }

};


/* =================================================
   ACTUALIZAR TOTAL
================================================= */

function actualizarTotal() {

    const rojo =
        Number(
            document.getElementById("redStat").value
        ) || 0;


    const verde =
        Number(
            document.getElementById("greenStat").value
        ) || 0;


    const azul =
        Number(
            document.getElementById("blueStat").value
        ) || 0;


    const total =
        rojo + verde + azul;


    document.getElementById(
        "total"
    ).textContent = total;


    document.getElementById(
        "infoRed"
    ).textContent = rojo;


    document.getElementById(
        "infoGreen"
    ).textContent = verde;


    document.getElementById(
        "infoBlue"
    ).textContent = azul;

}


/* Actualización automática */

document
    .getElementById("redStat")
    .addEventListener(
        "input",
        actualizarTotal
    );


document
    .getElementById("greenStat")
    .addEventListener(
        "input",
        actualizarTotal
    );


document
    .getElementById("blueStat")
    .addEventListener(
        "input",
        actualizarTotal
    );


/* =================================================
   CREAR MAZO
================================================= */

function crearMazo() {

    const rojo =
        Number(
            document.getElementById("redStat").value
        ) || 0;


    const verde =
        Number(
            document.getElementById("greenStat").value
        ) || 0;


    const azul =
        Number(
            document.getElementById("blueStat").value
        ) || 0;


    const nombre =
        document.getElementById(
            "characterName"
        ).value
        || "Mi Personaje";


    /*
     * Reiniciar el juego.
     */

    mazo = [];

    mano = [];

    descarte = [];

    turno = 1;


    /*
     * Crear cartas rojas.
     */

    for (let i = 0; i < rojo; i++) {

        mazo.push({

            id: siguienteID++,

            color: "rojo"

        });

    }


    /*
     * Crear cartas verdes.
     */

    for (let i = 0; i < verde; i++) {

        mazo.push({

            id: siguienteID++,

            color: "verde"

        });

    }


    /*
     * Crear cartas azules.
     */

    for (let i = 0; i < azul; i++) {

        mazo.push({

            id: siguienteID++,

            color: "azul"

        });

    }


    /*
     * Barajamos automáticamente
     * al crear el mazo.
     */

    barajar();


    document.getElementById(
        "playerName"
    ).textContent = nombre;


    document.getElementById(
        "turn"
    ).textContent = turno;


    actualizarInterfaz();

}


/* =================================================
   BARAJAR MAZO
================================================= */

function barajar() {

    /*
     * Fisher-Yates.
     *
     * IMPORTANTE:
     * solamente mezcla el contenido actual
     * de "mazo".
     *
     * NO toca la mano ni el descarte.
     */

    for (
        let i = mazo.length - 1;
        i > 0;
        i--
    ) {

        const j =
            Math.floor(
                Math.random() * (i + 1)
            );


        [
            mazo[i],
            mazo[j]
        ] =
        [
            mazo[j],
            mazo[i]
        ];

    }

}


/* =================================================
   BOTÓN BARAJAR MAZO
================================================= */

function barajarMazo() {

    if (mazo.length < 2) {

        alert(
            "No hay suficientes cartas en el mazo para barajar."
        );

        return;

    }


    barajar();


    actualizarInterfaz();


    alert(
        "El mazo ha sido barajado."
    );

}


/* =================================================
   ROBAR UNA
================================================= */

function robarUna() {

    if (mazo.length === 0) {

        alert(
            "El mazo está vacío."
        );

        return;

    }


    const carta =
        mazo.pop();


    mano.push(carta);


    actualizarInterfaz();

}


/* =================================================
   ROBAR CANTIDAD PERSONALIZADA
================================================= */

function robarMano() {

    let cantidad =
        Number(
            document.getElementById(
                "drawAmount"
            ).value
        );


    /*
     * Comprobamos que sea un número válido.
     */

    if (
        !Number.isInteger(cantidad) ||
        cantidad < 1
    ) {

        alert(
            "Introduce una cantidad válida."
        );

        return;

    }


    /*
     * No podemos robar más cartas
     * de las que quedan.
     */

    if (cantidad > mazo.length) {

        cantidad = mazo.length;

    }


    /*
     * Robamos exactamente la cantidad
     * disponible.
     */

    for (
        let i = 0;
        i < cantidad;
        i++
    ) {

        mano.push(
            mazo.pop()
        );

    }


    actualizarInterfaz();

}


/* =================================================
   SELECCIONAR CARTA
================================================= */

function seleccionarCarta(id) {

    const elemento =
        document.querySelector(
            `[data-id="${id}"]`
        );


    if (!elemento) return;


    elemento.classList.toggle(
        "selected"
    );

}


/* =================================================
   OBTENER SELECCIONADAS
================================================= */

function obtenerSeleccionadas() {

    const elementos =
        document.querySelectorAll(
            "#hand .card.selected"
        );


    return Array
        .from(elementos)
        .map(
            elemento =>
                Number(
                    elemento.dataset.id
                )
        );

}


/* =================================================
   DESCARTAR
================================================= */

function descartarSeleccionadas() {

    const ids =
        obtenerSeleccionadas();


    if (ids.length === 0) {

        alert(
            "Selecciona una o más cartas."
        );

        return;

    }


    const cartas =
        mano.filter(
            carta =>
                ids.includes(carta.id)
        );


    mano =
        mano.filter(
            carta =>
                !ids.includes(carta.id)
        );


    descarte.push(
        ...cartas
    );


    actualizarInterfaz();

}


/* =================================================
   USAR CARTAS
================================================= */

function usarSeleccionadas() {

    const ids =
        obtenerSeleccionadas();


    if (ids.length === 0) {

        alert(
            "Selecciona una o más cartas."
        );

        return;

    }


    const cartas =
        mano.filter(
            carta =>
                ids.includes(carta.id)
        );


    mano =
        mano.filter(
            carta =>
                !ids.includes(carta.id)
        );


    descarte.push(
        ...cartas
    );


    const resultado =
        cartas
            .map(
                carta =>
                    colores[
                        carta.color
                    ].simbolo
            )
            .join(" ");


    alert(
        "Cartas utilizadas:\n\n" +
        resultado
    );


    actualizarInterfaz();

}


/* =================================================
   DEVOLVER DESCARTE AL MAZO
================================================= */

function devolverDescarte() {

    if (descarte.length === 0) {

        alert(
            "No hay cartas en el descarte."
        );

        return;

    }


    /*
     * Movemos TODAS las cartas del
     * descarte al mazo.
     */

    mazo.push(
        ...descarte
    );


    /*
     * Vaciar el descarte.
     */

    descarte = [];


    /*
     * IMPORTANTE:
     *
     * NO barajamos automáticamente.
     *
     * Así el jugador decide cuándo
     * quiere barajar.
     */

    actualizarInterfaz();


    alert(
        "Las cartas del descarte han vuelto al mazo."
    );

}


/* =================================================
   NUEVO TURNO
================================================= */

function nuevoTurno() {

    turno++;


    document.getElementById(
        "turn"
    ).textContent = turno;

}


/* =================================================
   RENDERIZAR MANO
================================================= */

function renderizarMano() {

    const contenedor =
        document.getElementById(
            "hand"
        );


    contenedor.innerHTML = "";


    if (mano.length === 0) {

        contenedor.innerHTML = `
            <div class="empty">
                Tu mano está vacía.
            </div>
        `;

        return;

    }


    mano.forEach(carta => {

        const datos =
            colores[
                carta.color
            ];


        const elemento =
            document.createElement(
                "div"
            );


        elemento.className =
            `card ${datos.clase}`;


        elemento.dataset.id =
            carta.id;


        /*
         * CARTA TEMPORAL
         *
         * Más adelante aquí podremos
         * colocar la imagen real.
         */

        elemento.innerHTML = `

            <div class="card-symbol">
                ${datos.simbolo}
            </div>

            <div class="card-name">
                ${datos.nombre}
            </div>

            <div class="card-number">
                Carta #${carta.id}
            </div>

        `;


        elemento.addEventListener(
            "click",
            () =>
                seleccionarCarta(
                    carta.id
                )
        );


        contenedor.appendChild(
            elemento
        );

    });

}


/* =================================================
   RENDERIZAR DESCARTE
================================================= */

function renderizarDescarte() {

    const contenedor =
        document.getElementById(
            "discard"
        );


    contenedor.innerHTML = "";


    if (descarte.length === 0) {

        contenedor.innerHTML = `
            <div class="empty">
                No hay cartas descartadas.
            </div>
        `;

        return;

    }


    descarte.forEach(carta => {

        const datos =
            colores[
                carta.color
            ];


        const elemento =
            document.createElement(
                "div"
            );


        elemento.className =
            `card ${datos.clase}`;


        elemento.innerHTML = `

            <div class="card-symbol">
                ${datos.simbolo}
            </div>

            <div class="card-name">
                ${datos.nombre}
            </div>

            <div class="card-number">
                #${carta.id}
            </div>

        `;


        contenedor.appendChild(
            elemento
        );

    });

}


/* =================================================
   ACTUALIZAR INTERFAZ
================================================= */

function actualizarInterfaz() {

    document.getElementById(
        "deckCount"
    ).textContent =
        mazo.length;


    document.getElementById(
        "deckBig"
    ).textContent =
        mazo.length;


    renderizarMano();

    renderizarDescarte();

}


/* =================================================
   GUARDAR
================================================= */

function guardar() {

    const partida = {

        nombre:
            document.getElementById(
                "characterName"
            ).value,

        rojo:
            Number(
                document.getElementById(
                    "redStat"
                ).value
            ),

        verde:
            Number(
                document.getElementById(
                    "greenStat"
                ).value
            ),

        azul:
            Number(
                document.getElementById(
                    "blueStat"
                ).value
            ),

        mazo: mazo,

        mano: mano,

        descarte: descarte,

        turno: turno,

        siguienteID: siguienteID

    };


    localStorage.setItem(
        "rpgCardGame",
        JSON.stringify(partida)
    );


    alert(
        "Partida guardada en este navegador."
    );

}


/* =================================================
   CARGAR
================================================= */

function cargar() {

    const guardado =
        localStorage.getItem(
            "rpgCardGame"
        );


    if (!guardado) {

        alert(
            "No hay ninguna partida guardada."
        );

        return;

    }


    const partida =
        JSON.parse(
            guardado
        );


    document.getElementById(
        "characterName"
    ).value =
        partida.nombre;


    document.getElementById(
        "redStat"
    ).value =
        partida.rojo;


    document.getElementById(
        "greenStat"
    ).value =
        partida.verde;


    document.getElementById(
        "blueStat"
    ).value =
        partida.azul;


    mazo =
        partida.mazo || [];


    mano =
        partida.mano || [];


    descarte =
        partida.descarte || [];


    turno =
        partida.turno || 1;


    siguienteID =
        partida.siguienteID || 1;


    document.getElementById(
        "playerName"
    ).textContent =
        partida.nombre;


    document.getElementById(
        "turn"
    ).textContent =
        turno;


    actualizarTotal();

    actualizarInterfaz();


    alert(
        "Partida cargada."
    );

}


/* =================================================
   INICIO
================================================= */

actualizarTotal();

crearMazo();

</script>

</body>
</html>
```