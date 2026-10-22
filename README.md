```html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
* { box-sizing: border-box; }

body {
  margin: 0;
  background: transparent;
  font-family: Georgia, serif;
}

.galeria {
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 12px;
}

.arco {
  position: relative;
  width: min(100%, 360px);
  aspect-ratio: 3 / 4;
  overflow: hidden;
  border: 2px solid #b9a477;
  border-radius: 180px 180px 8px 8px;
  background: #62694b;
}

.foto {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transform: scale(1);
  transition: opacity 1.2s ease, transform 5s ease;
}

.foto.activa {
  opacity: 1;
  transform: scale(1.12);
}
</style>
</head>
<body>

<div class="galeria">
  <div class="arco">
    <img class="foto activa" src="./foto1.jpg" alt="Fotografía 1">
    <img class="foto" src="./foto2.jpg" alt="Fotografía 2">
    <img class="foto" src="./foto3.jpg" alt="Fotografía 3">
    <img class="foto" src="./foto4.jpg" alt="Fotografía 4">
  </div>
</div>

<script>
const fotos = document.querySelectorAll('.foto');
let actual = 0;

setInterval(() => {
  fotos[actual].classList.remove('activa');
  actual = (actual + 1) % fotos.length;
  fotos[actual].classList.add('activa');
}, 5000);
</script>

</body>
</html>
```
