
<html>
<body>
	
	

<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<title>Simulador de Piano</title>
<style>
  .tecla {
    width: 60px;
    height: 200px;
    border: 1px solid #000;
    float: left;
    margin: 5px;
    background-color: white;
  }
  .tecla.preta {
    width: 40px;
    height: 140px;
    background-color: black;
    margin-left: -20px;
    margin-right: -20px;
    z-index: 1;
  }
</style>
</head>
<body>

<div id="piano">
  <div class="tecla" onclick="tocarSom('C')"></div>
  <div class="tecla preta" onclick="tocarSom('C#')"></div>
  <div class="tecla" onclick="tocarSom('D')"></div>
 <!-- Teclas brancas -->
<div class="tecla" onclick="tocarSom('E')"></div>
<div class="tecla" onclick="tocarSom('F')"></div>
<div class="tecla preta" onclick="tocarSom('F#')"></div>
<div class="tecla" onclick="tocarSom('G')"></div>
<div class="tecla preta" onclick="tocarSom('G#')"></div>
<div class="tecla" onclick="tocarSom('A')"></div>
<div class="tecla preta" onclick="tocarSom('A#')"></div>
<div class="tecla" onclick="tocarSom('B')"></div>
<div class="tecla" onclick="tocarSom('C2')"></div> <!-- Esta seria a próxima oitava -->
<!-- Continuação das teclas brancas e pretas para a próxima oitava -->
<div class="tecla" onclick="tocarSom('C3')"></div>
<div class="tecla preta" onclick="tocarSom('C#3')"></div>
<div class="tecla" onclick="tocarSom('D3')"></div>
<div class="tecla preta" onclick="tocarSom('D#3')"></div>
<div class="tecla" onclick="tocarSom('E3')"></div>
<div class="tecla" onclick="tocarSom('F3')"></div>
<div class="tecla preta" onclick="tocarSom('F#3')"></div>
<div class="tecla" onclick="tocarSom('G3')"></div>
<div class="tecla preta" onclick="tocarSom('G#3')"></div>
<div class="tecla" onclick="tocarSom('A3')"></div>
<div class="tecla preta" onclick="tocarSom('A#3')"></div>
<div class="tecla" onclick="tocarSom('B3')"></div>
<div class="tecla" onclick="tocarSom('C4')"></div> <!-- Início da próxima oitava -->

<!-- Adicione mais teclas pretas entre as teclas brancas conforme necessário -->
 <!-- Adicione mais teclas aqui -->
</div>

<script>
  function tocarSom(nota) {
    var audio = new Audio('audios/' + nota + '.mp3');
    audio.play();
  }
Página HTML 
	<script type="text/javascript">
		<!--
		
			/* escreva seu código aqui.*/
			
		//-->     function tocarSom(nota) {
  // Verifique se o arquivo de áudio existe
  var audio = new Audio('audios/' + nota + '.mp3');
  audio.oncanplaythrough = function() {
    audio.play();
  };
  audio.onerror = function() {
    console.log("Erro ao carregar o arquivo de áudio para a nota: " + nota);
  };
  // Pré-carregue o áudio para reprodução mais rápida
  audio.preload = 'auto';
  // Defina o volume (0.0 mudo, 1.0 máximo)
  audio.volume = 0.5;
}
          document.addEventListener('keydown', function(event) {
  var nota;
  switch (event.key) {
    case 'a':
      nota = 'C';
      break;
    case 'w':
      nota = 'C#';
      break;
    // Adicione casos para outras teclas
    default:
      return; // Saia da função caso seja uma tecla não mapeada
  }
  tocarSom(nota);
});

</script>

</body>
</html>		
