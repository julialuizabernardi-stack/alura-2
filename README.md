

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Agricultura</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background: #1b4332;
            color: white;
            overflow: hidden;
        }

        .slide {
            display: none;
            width: 100vw;
            height: 100vh;

            padding: 60px 12%;

            justify-content: center;
            align-items: center;
            flex-direction: column;

            text-align: center;

            background: linear-gradient(
                135deg,
                #1b4332,
                #40916c
            );
        }

        .ativo {
            display: flex;
        }

        h1 {
            font-size: 60px;
            color: #d8f3dc;
            margin-bottom: 25px;
        }

        h2 {
            font-size: 45px;
            color: #d8f3dc;
            margin-bottom: 30px;
        }

        p {
            font-size: 23px;
            line-height: 1.6;
            max-width: 850px;
        }

        ul {
            text-align: left;
            font-size: 23px;
            line-height: 1.8;
            max-width: 800px;
        }

        li {
            margin-bottom: 8px;
        }

        .destaque {
            color: #ffd166;
            font-weight: bold;
        }

        .controles {
            position: fixed;
            bottom: 20px;
            width: 100%;

            display: flex;
            justify-content: center;
            align-items: center;

            gap: 20px;
        }

        button {
            padding: 12px 25px;

            border: none;
            border-radius: 8px;

            background: #ffd166;
            color: #1b4332;

            font-size: 17px;
            font-weight: bold;

            cursor: pointer;
        }

        button:hover {
            background: #fff0a8;
        }

        #contador {
            font-size: 18px;
        }

        .emoji {
            font-size: 70px;
            margin-bottom: 20px;
        }
    </style>
</head>

<body>

    <!-- SLIDE 1 -->
    <section class="slide ativo">

        <div class="emoji">🌱</div>

        <h1>Agricultura</h1>

        <p>
            A agricultura é uma atividade fundamental
            para a sociedade e para a economia.
        </p>

    </section>


    <!-- SLIDE 2 -->
    <section class="slide">

        <div class="emoji">🌾</div>

        <h2>O que é Agricultura?</h2>

        <p>
            Agricultura é a atividade de cultivar a terra
            para produzir alimentos, matérias-primas
            e outros produtos utilizados pela população.
        </p>

    </section>


    <!-- SLIDE 3 -->
    <section class="slide">

        <div class="emoji">🚜</div>

        <h2>Importância da Agricultura</h2>

        <ul>
            <li>Produz alimentos para a população.</li>
            <li>Gera empregos e renda.</li>
            <li>Fornece matérias-primas para as indústrias.</li>
            <li>Contribui para a economia do país.</li>
        </ul>

    </section>


    <!-- SLIDE 4 -->
    <section class="slide">

        <div class="emoji">🌱</div>

        <h2>Agricultura Sustentável</h2>

        <p>
            A agricultura sustentável busca produzir alimentos
            utilizando os recursos naturais de forma responsável.
        </p>

        <p style="margin-top: 25px;">
            É importante preservar o
            <span class="destaque">
                solo, a água e a biodiversidade.
            </span>
        </p>

    </section>


    <!-- SLIDE 5 -->
    <section class="slide">

        <div class="emoji">🌎</div>

        <h2>Conclusão</h2>

        <p>
            A agricultura é essencial para a vida humana.
            Ela fornece alimentos, gera empregos e movimenta
            a economia.
        </p>

        <p style="margin-top: 25px;">
            <span class="destaque">
                Produzir hoje pensando no futuro!
            </span>
        </p>

    </section>


    <!-- CONTROLES -->

    <div class="controles">

        <button onclick="anterior()">
            ← Anterior
        </button>

        <span id="contador">
            1 / 5
        </span>

        <button onclick="proximo()">
            Próximo →
        </button>

    </div>


    <script>

        const slides = document.querySelectorAll(".slide");

        let atual = 0;


        function mostrarSlide(numero) {

            slides.forEach(slide => {
                slide.classList.remove("ativo");
            });

            slides[numero].classList.add("ativo");

            document.getElementById("contador").textContent =
                `${numero + 1} / ${slides.length}`;
        }


        function proximo() {

            if (atual < slides.length - 1) {
                atual++;
                mostrarSlide(atual);
            }

        }


        function anterior() {

            if (atual > 0) {
                atual--;
                mostrarSlide(atual);
            }

        }


        document.addEventListener("keydown", function(event) {

            if (event.key === "ArrowRight") {
                proximo();
            }

            if (event.key === "ArrowLeft") {
                anterior();
            }

        });

    </script>

</body>
</html>
