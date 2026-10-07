# guilherme-estrafalhote
<!DOCTYPE html>
<html lang="pt-PT">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Guilherme Teixeira Estrafalhote</title>

    <meta
        name="description"
        content="Perfil desportivo público de Guilherme Teixeira Estrafalhote."
    >

    <link rel="stylesheet" href="style.css">
</head>

<body>

<header class="hero">
    <div class="container">

        <p class="eyebrow">PERFIL DESPORTIVO</p>

        <h1>
            Guilherme Teixeira<br>
            Estrafalhote
        </h1>

        <p class="subtitle">
            Futebol · Formação · Portugal
        </p>

        <div class="badges">
            <span>SC Braga</span>
            <span>Defesa</span>
        </div>

    </div>
</header>


<main class="container">

    <section class="privacy">
        <strong>Privacidade</strong>

        <p>
            Este site reúne apenas informação pública relacionada
            com o percurso desportivo. Não são apresentados contactos,
            morada, escola ou outros dados pessoais desnecessários.
        </p>
    </section>


    <section class="grid">

        <article class="card">

            <h2>Estado atual</h2>

            <div class="info">
                <span>Clube</span>
                <strong id="club">SC Braga</strong>
            </div>

            <div class="info">
                <span>Posição</span>
                <strong id="position">Defesa</strong>
            </div>

            <div class="info">
                <span>Pé preferencial</span>
                <strong id="foot">Esquerdo</strong>
            </div>

            <div class="info">
                <span>Última atualização</span>
                <strong id="updated">—</strong>
            </div>

        </article>


        <article class="card">

            <h2>Resumo</h2>

            <p id="summary">
                A carregar informação...
            </p>

        </article>

    </section>


    <section class="card">

        <div class="section-title">
            <h2>Percurso desportivo</h2>
            <span>Registos públicos</span>
        </div>

        <div id="history"></div>

    </section>


    <section class="card">

        <div class="section-title">
            <h2>Atividade recente</h2>
            <span>Atualização automática</span>
        </div>

        <div id="recent"></div>

    </section>


    <section class="card">

        <h2>Fontes</h2>

        <p class="muted">
            Consulta sempre as fontes originais para confirmar a informação.
        </p>

        <ul id="sources"></ul>

    </section>

</main>


<footer>

    <div class="container">

        Site atualizado automaticamente.

        <br>

        Última atualização:
        <span id="footerDate">—</span>

    </div>

</footer>


<script src="script.js"></script>

</body>
</html>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background: #f4f5f7;
    color: #17191d;

    font-family:
        Arial,
        Helvetica,
        sans-serif;

    line-height: 1.6;
}


.container {
    width: min(1050px, calc(100% - 32px));
    margin: auto;
}


/* HERO */

.hero {
    background: #101114;
    color: white;

    padding: 80px 0 65px;
}


.eyebrow {
    font-size: 13px;
    letter-spacing: 4px;
    opacity: .65;
}


.hero h1 {
    font-size: clamp(42px, 7vw, 82px);
    line-height: .95;

    margin: 18px 0;
}


.subtitle {
    font-size: 20px;
    color: #c9ccd2;
}


.badges {
    display: flex;
    gap: 10px;

    margin-top: 30px;
}


.badges span {
    border: 1px solid #555a63;

    border-radius: 50px;

    padding: 7px 15px;

    font-size: 14px;
}


/* PRIVACY */

.privacy {
    background: white;

    border-left: 4px solid #111;

    padding: 18px 20px;

    margin: 30px 0;

    border-radius: 10px;
}


.privacy p {
    margin-bottom: 0;
}


/* CARDS */

.grid {
    display: grid;

    grid-template-columns: 1fr 1fr;

    gap: 20px;
}


.card {
    background: white;

    border: 1px solid #e2e4e8;

    border-radius: 15px;

    padding: 25px;

    margin-bottom: 20px;

    box-shadow: 0 5px 20px rgba(0,0,0,.04);
}


.card h2 {
    margin-top: 0;
}


/* INFORMAÇÃO */

.info {
    display: flex;

    justify-content: space-between;

    gap: 20px;

    padding: 12px 0;

    border-bottom: 1px solid #eee;
}


.info span {
    color: #777;
}


.info strong {
    text-align: right;
}


/* TÍTULOS */

.section-title {
    display: flex;

    justify-content: space-between;

    align-items: center;
}


.section-title span {
    color: #777;

    font-size: 14px;
}


/* HISTÓRICO */

.season {
    display: flex;

    justify-content: space-between;

    padding: 15px 0;

    border-bottom: 1px solid #eee;
}


.season:last-child {
    border-bottom: 0;
}


.season strong {
    display: block;
}


.stats {
    color: #777;

    text-align: right;
}


/* ATIVIDADE */

.activity {
    border: 1px solid #e5e7ea;

    border-radius: 10px;

    padding: 15px;

    margin: 10px 0;
}


.activity strong {
    display: block;

    margin-bottom: 4px;
}


/* FONTES */

.sources {
    padding-left: 20px;
}


.sources li {
    margin: 10px 0;
}


.sources a {
    color: #111;
}


/* FOOTER */

footer {
    color: #777;

    padding: 30px 0 60px;
}


/* MOBILE */

@media (max-width: 700px) {

    .grid {
        grid-template-columns: 1fr;
    }

    .hero {
        padding: 55px 0;
    }

    .hero h1 {
        font-size: 48px;
    }

    .section-title {
        display: block;
    }

    .season {
        display: block;
    }

    .stats {
        text-align: left;

        margin-top: 5px;
    }

}
async function carregarDados() {

    try {

        const resposta = await fetch(
            "data.json?v=" + Date.now()
        );

        const dados = await resposta.json();


        // Informações principais

        document.getElementById("club").textContent =
            dados.current.club;

        document.getElementById("position").textContent =
            dados.current.position;

        document.getElementById("foot").textContent =
            dados.current.foot;

        document.getElementById("updated").textContent =
            dados.updated_at;

        document.getElementById("footerDate").textContent =
            dados.updated_at;

        document.getElementById("summary").textContent =
            dados.summary;


        // Histórico

        const history =
            document.getElementById("history");


        history.innerHTML = "";


        dados.history.forEach(epoca => {

            const div =
                document.createElement("div");

            div.className = "season";


            div.innerHTML = `

                <div>

                    <strong>
                        ${epoca.season}
                    </strong>

                    <span>
                        ${epoca.team}
                    </span>

                </div>

                <div class="stats">

                    ${epoca.games ?? "—"} jogos

                    ·

                    ${epoca.goals ?? "—"} golos

                </div>

            `;


            history.appendChild(div);

        });


        // Atividade recente

        const recent =
            document.getElementById("recent");


        recent.innerHTML = "";


        dados.recent.forEach(item => {

            const div =
                document.createElement("div");

            div.className = "activity";


            div.innerHTML = `

                <strong>
                    ${item.title}
                </strong>

                <span>
                    ${item.detail}
                </span>

            `;


            recent.appendChild(div);

        });


        // Fontes

        const sources =
            document.getElementById("sources");


        sources.innerHTML = "";


        dados.sources.forEach(source => {

            const li =
                document.createElement("li");


            li.innerHTML = `

                <a
                    href="${source.url}"
                    target="_blank"
                    rel="noopener"
                >
                    ${source.name}
                </a>

            `;


            sources.appendChild(li);

        });

    }

    catch (erro) {

        console.error(erro);

        document.getElementById("summary").textContent =
            "Não foi possível carregar os dados.";

    }

}


carregarDados();
{
    "updated_at": "2026-10-08",

    "current": {
        "club": "SC Braga",
        "position": "Defesa",
        "foot": "Esquerdo"
    },

    "summary": "Guilherme Teixeira Estrafalhote é um jogador português de futebol de formação associado ao SC Braga. Os registos públicos identificam-no como defesa e documentam o seu percurso por equipas de formação e participações em competições.",

    "history": [

        {
            "season": "2026/27",
            "team": "SC Braga",
            "games": 2,
            "goals": 0
        },

        {
            "season": "2025/26",
            "team": "SC Braga",
            "games": 21,
            "goals": 1
        },

        {
            "season": "2024/25",
            "team": "Núcleo SCP Solar do Norte",
            "games": 34,
            "goals": 11
        },

        {
            "season": "2023/24",
            "team": "Núcleo Sporting Aveiro",
            "games": 34,
            "goals": 17
        },

        {
            "season": "2022/23",
            "team": "NS Ançã",
            "games": 26,
            "goals": 33
        },

        {
            "season": "2021/22",
            "team": "NS Ançã",
            "games": null,
            "goals": null
        },

        {
            "season": "2020/21",
            "team": "NS Ançã",
            "games": null,
            "goals": null
        },

        {
            "season": "2019/20",
            "team": "Renascente S. Teotónio",
            "games": null,
            "goals": null
        },

        {
            "season": "2018/19",
            "team": "Odemirense",
            "games": null,
            "goals": null
        }

    ],

    "recent": [

        {
            "title": "SC Braga — 2026/27",
            "detail": "Registos públicos recentes indicam participação pelo SC Braga em competições de formação."
        },

        {
            "title": "Federação Portuguesa de Futebol",
            "detail": "Existem registos públicos de participação em jogos de formação pelo SC Braga."
        },

        {
            "title": "Seleção Distrital Sub-13 de Braga",
            "detail": "O nome surge em convocatórias públicas da Associação de Futebol de Braga."
        },

        {
            "title": "Portugal Under Cup Monção 2026",
            "detail": "O jogador aparece no plantel do SC Braga na competição Sub-13."
        }

    ],

    "sources": [

        {
            "name": "ZeroZero — perfil e estatísticas",
            "url": "https://www.zerozero.pt/jogador/guilherme-estrafalhote/1126446"
        },

        {
            "name": "Federação Portuguesa de Futebol",
            "url": "https://resultados.fpf.pt/"
        },

        {
            "name": "Associação de Futebol de Braga",
            "url": "https://afbraga.fpf.pt/"
        },

        {
            "name": "Portugal Under Cup",
            "url": "https://edicao2026.undercup.pt/"
        }

    ]
}
.github
└── workflows
    └── update.yml
    name: Atualização semanal

on:

  schedule:

    - cron: "0 7 * * 1"

  workflow_dispatch:


permissions:

  contents: write


jobs:

  update:

    runs-on: ubuntu-latest

    steps:

      - name: Download do código
        uses: actions/checkout@v4


      - name: Configurar Python
        uses: actions/setup-python@v5

        with:
          python-version: "3.12"


      - name: Instalar dependências
        run: |
          pip install requests


      - name: Atualizar dados
        run: |
          python update.py


      - name: Guardar alterações
        run: |

          git config user.name "weekly-update"

          git config user.email \
            "actions@users.noreply.github.com"

          git add data.json

          git diff --cached --quiet || \
            git commit -m "Atualização semanal"

          git push
          import json
import requests
from datetime import date


SOURCES = [

    "https://www.zerozero.pt/jogador/guilherme-estrafalhote/1126446",

    "https://resultados.fpf.pt/",

    "https://afbraga.fpf.pt/",

    "https://edicao2026.undercup.pt/"

]


with open(
    "data.json",
    "r",
    encoding="utf-8"
) as file:

    data = json.load(file)


reachable = 0


for url in SOURCES:

    try:

        response = requests.get(
            url,
            timeout=20,

            headers={
                "User-Agent":
                "GuilhermeSiteUpdater/1.0"
            }
        )

        response.raise_for_status()

        reachable += 1

    except Exception as error:

        print(
            "Erro:",
            url,
            error
        )


data["updated_at"] = date.today().isoformat()


data["source_check"] = {

    "sources_checked":
        len(SOURCES),

    "sources_reachable":
        reachable

}


with open(
    "data.json",
    "w",
    encoding="utf-8"
) as file:

    json.dump(
        data,
        file,
        ensure_ascii=False,
        indent=4
    )


print(
    "Atualização concluída."
)
guilherme-site/
│
├── index.html
├── style.css
├── script.js
├── data.json
├── update.py
│
└── .github/
    └── workflows/
        └── update.yml
