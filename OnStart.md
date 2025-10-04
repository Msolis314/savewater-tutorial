# ¡Armemos el bloque **on start**!

## @explicitHints true
## @unplugged
En este tutorial crearás el bloque **`on start`** que:
- Cambia el color de fondo.
- Carga un **tilemap**.
- Crea el sprite del jugador **Reparador** (de tipo `Player`).
- Llama funciones auxiliares (`inicio`, `crearJugador`, `caminar`, `crearMuros`).
- Inicia una cuenta regresiva de **120 s**.

Al final tendrás la estructura base del juego lista para empezar.

```template
// Plantilla de arranque: crea las funciones que vamos a “llamar” desde on start.
function inicio () { }
function crearJugador (personaje: Sprite) { }
function caminar () { }
function crearMuros () { }

let Reparador: Sprite = null
```

---

## Paso 1: agrega el bloque **on start**
Arrastra el bloque **`on start`** desde *Sprites* → *Game* (o desde *Basic*, según el editor) al área de trabajo.  
Dentro de él construiremos toda la lógica de arranque.

### ~hint
Si ya tienes un `on start`, reutilízalo. Solo debe existir **uno** por proyecto.
### ~

```blocks
// (Aún vacío)
```

---

## Paso 2: establece el color de fondo
Dentro de **on start**, añade **`set background color to …`** y elige el color que prefieras.

```blocks
// on start
scene.setBackgroundColor(7)
```

### ~hint
El número del color puede variar. Usa el selector y no te preocupes por el valor exacto.
### ~

---

## Paso 3: carga el **tilemap**
Añade **`set tilemap to …`** y selecciona/crea tu mapa (por ejemplo, `nivel1`).

```blocks
// on start
scene.setBackgroundColor(7)
tiles.setTilemap(tilemap`nivel1`)
```

### ~hint
Si no tienes un tilemap aún, crea uno rápido con el editor y guárdalo como `nivel1`.
### ~

---

## Paso 4: crea el sprite **Reparador** (tipo `Player`)
1) Crea la variable **`Reparador`**.  
2) Usa **`set Reparador to sprite of kind Player`**.  
3) Dibuja o pega la imagen del personaje.

```blocks
let Reparador: Sprite = null
// on start
scene.setBackgroundColor(7)
tiles.setTilemap(tilemap`nivel1`)
Reparador = sprites.create(img`
    . . . . . . . . . . . . . . . .
    // ← Sustituye este arte por el tuyo
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
```

### ~hint
Asegúrate de que el **kind** sea `Player` para que luego puedas controlar al personaje.
### ~

---

## Paso 5: llama a **inicio**
Añade el bloque **`call inicio`** debajo de la creación del sprite.

```blocks
let Reparador: Sprite = null
// on start
scene.setBackgroundColor(7)
tiles.setTilemap(tilemap`nivel1`)
Reparador = sprites.create(img`
`, SpriteKind.Player)
inicio()
```

### ~hint
`inicio()` es una función vacía en la plantilla. Más adelante podrás llenarla con lógica de configuración.
### ~

---

## Paso 6: pasa el jugador a **crearJugador**
Añade **`call crearJugador Reparador`** para enviar el sprite a esa función.

```blocks
let Reparador: Sprite = null
// on start
scene.setBackgroundColor(7)
tiles.setTilemap(tilemap`nivel1`)
Reparador = sprites.create(img`
`, SpriteKind.Player)
inicio()
crearJugador(Reparador)
```

### ~hint
Esto te permite inicializar posición, animaciones o vidas dentro de `crearJugador(personaje)`.
### ~

---

## Paso 7: llama a **caminar** y **crearMuros**
Añade los bloques **`call caminar`** y **`call crearMuros`** en ese orden.

```blocks
let Reparador: Sprite = null
// on start
scene.setBackgroundColor(7)
tiles.setTilemap(tilemap`nivel1`)
Reparador = sprites.create(img`
`, SpriteKind.Player)
inicio()
crearJugador(Reparador)
caminar()
crearMuros()
```

### ~hint
Más adelante, dentro de estas funciones, podrás definir controles, velocidad y obstáculos del mapa.
### ~

---

## Paso 8: inicia la cuenta regresiva
Cierra el bloque con **`start countdown 120 (s)`**.

```blocks
let Reparador: Sprite = null
// on start
scene.setBackgroundColor(7)
tiles.setTilemap(tilemap`nivel1`)
Reparador = sprites.create(img`
`, SpriteKind.Player)
inicio()
crearJugador(Reparador)
caminar()
crearMuros()
info.startCountdown(120)
```

### ~hint
Puedes ajustar los segundos para cambiar la dificultad del juego.
### ~

---

## ¡Listo!
Tu bloque **`on start`** ya:
1. Configura el entorno (fondo y tilemap).  
2. Crea al jugador **Reparador** (`Player`).  
3. Llama funciones de organización del proyecto.  
4. Arranca un temporizador de 120 s.

> En el siguiente paso del tutorial podrás completar el contenido de `inicio`, `crearJugador`, `caminar` y `crearMuros`.