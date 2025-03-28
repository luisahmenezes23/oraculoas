<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Oráculo do Tarot</title>

    <style>

.logo {
    width: 200px; /* Ajuste o tamanho como preferir */
    margin-bottom: 0px; /* Espaço entre a logo e o título */
}
        @font-face {
            font-family: "Storyboo";
            src: url("fonts/STORYBOO.TTF");
        }
        @font-face {
            font-family: "GaretBook";
            src: url("fonts/GARET-BOOK.TTF");
        }

        body {
    font-family: "GaretBook", Arial, sans-serif;
    background-image: url('images/fundo.png'); /* Altere aqui o nome da sua imagem */
    background-size: cover; /* cobre a tela inteira */
    background-repeat: no-repeat; /* não repete a imagem */
    background-position: center; /* centraliza a imagem */
    color: #fff;
    text-align: center;
    padding: 20px;
    backdrop-filter: brightness(0.7); /* escurece suavemente para melhor leitura */
}
        
        .titulo {
            font-family: "Storyboo", Arial, sans-serif;
            font-size: 30px;
            margin-bottom: 30px;
        }
        
        .cartas {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .cartas img {
            width: 100px;
            cursor: pointer;
            transition: transform 0.3s;
        }
        
        .cartas img:hover {
            transform: translateY(-10px);
        }
        
        .resultado {
    max-width: 900px; /* pode ajustar conforme necessidade */
    margin: 20px auto;
    padding: 20px;
    background: #292929;
    border-radius: 10px;
    display: none;
    text-align: left;
    line-height: 1.6;
    display: flex; /* alinha lado a lado */
    align-items: flex-start; /* alinha imagem e texto pelo topo */
    gap: 20px; /* espaço entre imagem e texto */
}

        .resultado h2 {
            font-family: "Storyboo", Arial, sans-serif;
            font-size: 25px;
            text-align: center;
            margin-bottom: 15px;
            color: #fff;
        }

        .resultado p {
            font-family: "GaretBook", Arial, sans-serif;
            font-size: 15px;
            margin-bottom: 10px;
        }

        .cta {
            margin-top: 30px;
            padding: 15px;
            background-color: #5e4b8b;
            border-radius: 8px;
            font-family: "GaretBook", Arial, sans-serif;
        }

        .cta a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
        }
    </style>
</head>

<body>

<img src="images/logo.png" alt="Logo do Oráculo" class="logo">

<div class="titulo">🔮 O oráculo está aberto...
se concentre e escolha uma carta! 🔮</div>

<div class="cartas">
    <!-- 17 cartas iguais -->
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">
<img src="https://i.pinimg.com/736x/51/70/ff/5170ffda8f8c80447d04f380babd1cf5.jpg" onclick="sortearCarta()">

</div>

<div class="resultado" id="resultado"></div>

<div class="cta">
    Que tal uma tiragem personalizada comigo?<br>
    <a href="http://wa.me/5532936180254">Tiragens a partir de R$ 15 para te ajudar em qualquer assunto!</a>
</div>

<script>
    const cartas = [
{
    arcano: 0,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_285/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Louco-.jpg",
    nome: "O Louco",
    simNao: "Sim, mas com incerteza. Representa liberdade e imprevisibilidade.",
    atributos: "Ligação com o Divino, pureza, inocência, novidade, desapego, criatividade, intuição, novos ciclos, originalidade.",
    desafios: "Caos, desordem, impulsividade, irresponsabilidade, imaturidade, vícios, incoerência, preguiça, desatenção.",
    risco: "Incerteza e imprevisibilidade.",
    objetivo: "Busca espiritual, transcendência.",
    tarefa: "Aceitar o desconhecido e seguir a intuição.",
    arquetipo: "Espontaneidade, liberdade, loucura criativa.",
    personalidade: "Indivíduos aventureiros, criativos, impulsivos e otimistas, mas que podem ser ingênuos ou irresponsáveis.",
    caracteristicasFisicas: "Pessoa jovial, cabelos desarrumados ou despenteados, vestimenta despojada, olhar curioso e expressivo.",
    temporalidade: "Início de algo inesperado e rápido. Primavera, mudanças bruscas e repentinas. Agora ou dentro de 0 a 1 ano.",
    amor: "Indica espontaneidade, novidades e relacionamentos não convencionais. Pode sugerir instabilidade.",
    dinheiro: "Sugere novas oportunidades, mas também a necessidade de cautela com impulsividade financeira.",
    saude: "Traz vitalidade e energia, mas alerta contra comportamentos imprudentes."
  },
  {
    arcano: 1,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_285/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Mago-.jpg",
    nome: "O Mago",
    simNao: "Sim",
    atributos: "Liberdade, independência, inteligência, eloquência, habilidades, iniciativa",
    desafios: "Egoísmo, superficialidade, mau uso do poder, charlatanismo",
    risco: "Mania de grandeza, fantasias de poder, manipulação",
    objetivo: "Maestria, autoconhecimento, realização pessoal",
    tarefa: "Agir, tomar a iniciativa e realizar tarefas com maestria",
    arquetipo: "O Criador, o Mestre",
    personalidade: "Confiante, persuasivo, estratégico, hábil em comunicação, inteligente, mas pode ser manipulador e arrogante",
    caracteristicasFisicas: "Pessoa de porte magro ou atlético, mãos expressivas, olhar penetrante e cativante, cabelo bem cuidado, postura segura",
    temporalidade: "Verão, período de até 1 ano, pode indicar algo acontecendo rapidamente, dentro de semanas ou meses",
    amor: "Indica charme, poder de sedução e controle sobre o relacionamento. Pode sugerir manipulação",
    dinheiro: "Oportunidade de crescimento, uso de habilidades para o sucesso, necessidade de estratégia",
    saude: "Energia para recuperação, equilíbrio entre mente e corpo"
  },
  {
    arcano: 2,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_289/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Sacerdotisa-.jpg",
    nome: "A Sacerdotisa",
    simNao: "Neutro",
    atributos: "Intuição, sabedoria, proteção, mistério, conexão espiritual",
    desafios: "Falsidade, insegurança, falta de objetividade, omissão",
    risco: "Hesitação, fuga da realidade, indecisão prolongada",
    objetivo: "Certeza intuitiva, compreensão profunda, conhecimento oculto",
    tarefa: "Esperar pacientemente pelo momento certo e ouvir a intuição",
    arquetipo: "A Rainha do Céu, a Guardiã dos Mistérios",
    personalidade: "Reservada, enigmática, sábia, observadora, paciente, confiável, mas pode ser distante ou introspectiva demais",
    caracteristicasFisicas: "Aparência misteriosa e atraente, cabelos longos e escuros, olhos profundos e expressivos, postura elegante e serena",
    temporalidade: "Outono e inverno, representa períodos longos, podendo indicar eventos que levam de 6 meses a 2 anos para se concretizar",
    amor: "Relações profundas, espirituais e intuitivas. Pode indicar segredos ou falta de comunicação clara",
    dinheiro: "Sugere observação antes da ação, estudo e planejamento estratégico. Pode indicar segredos financeiros",
    saude: "Necessidade de equilíbrio emocional e mental, conexão com práticas espirituais para autodescoberta"
  },
  {
    arcano: 3,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_290/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Imperatriz-.jpg",
    nome: "A Imperatriz",
    simNao: "Sim",
    atributos: "Amor, abertura, alegria, proteção, generosidade, dedicação, produtividade, gestação",
    desafios: "Tirania, futilidade, indolência, fofocas, intrigas, mau humor, falta de tato",
    risco: "Crescimento desordenado, instabilidade",
    objetivo: "Energia vital e crescimento, renovação cíclica, afirmação da vida",
    tarefa: "Ser fértil, trazer o novo ao mundo",
    arquetipo: "A Mãe (Mãe Natureza)",
    personalidade: "Afetuosa, criativa, carismática, acolhedora, mas pode ser possessiva e indulgente",
    caracteristicasFisicas: "Fisionomia serena, cabelos volumosos ou ondulados, expressão maternal, vestes luxuosas e em tons terrosos",
    temporalidade: "Primavera e outono, ciclos de 9 meses, gestação, renovação",
    amor: "Relacionamentos estáveis e férteis, amor incondicional, maternidade ou desenvolvimento de laços emocionais",
    dinheiro: "Prosperidade, criatividade nos negócios, sucesso em empreendimentos ligados à arte e ao cuidado",
    saude: "Boa saúde, vitalidade, fertilidade, necessidade de equilíbrio emocional"
  },
  {
    arcano: 4,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_293/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Imperador-.jpg",
    nome: "O Imperador",
    simNao: "Sim",
    atributos: "Objetividade, praticidade, responsabilidade, poder, concretização, trabalho, bens materiais, prosperidade",
    desafios: "Tirania, manipulação, mau uso do poder, inflexibilidade, pragmatismo, mau chefe",
    risco: "Teimosia, perfeccionismo, endurecimento, rigidez",
    objetivo: "Criar a ordem e um ambiente seguro, estrutura, capacidade de resistência",
    tarefa: "Concretizar ideias, intenções e desejos de modo consequente, perseverança",
    arquetipo: "O Pai (Estado de Pai)",
    personalidade: "Líder nato, disciplinado, confiável, autoritário, pode ser inflexível e controlador",
    caracteristicasFisicas: "Postura imponente, traços marcantes, cabelos curtos ou grisalhos, vestes formais, olhar penetrante",
    temporalidade: "Inverno, ciclos longos, estruturação de longo prazo, períodos de 4 anos",
    amor: "Relacionamento baseado em estrutura e segurança, pode indicar figuras paternas ou relações tradicionais",
    dinheiro: "Sucesso em carreiras estruturadas, liderança firme, estabilidade financeira",
    saude: "Boa resistência física, mas propensão a estresse e problemas relacionados ao excesso de controle"
  },
  {
    arcano: 5,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_288/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Hierofante-.jpg",
    nome: "O Papa",
    simNao: "Neutro",
    atributos: "Responsabilidade, casamento, proteção e amparo espiritual, dignidade, conhecimento, confiança, mestre espiritual",
    desafios: "Arrogância espiritual, presunção, falso moralismo, fanatismo",
    risco: "Pseudodivindade, presunção, 'pretensão de ser guru'",
    objetivo: "Orientação espiritual e sabedoria",
    tarefa: "Prestar atenção e respeitar o notório e o oculto, busca de sentido",
    arquetipo: "O Santo",
    personalidade: "Sábio, tradicionalista, conselheiro, espiritualizado, pode ser dogmático e rígido",
    caracteristicasFisicas: "Expressão serena e respeitável, vestes cerimoniais, cabelos e barba bem cuidados, postura ereta e digna",
    temporalidade: "Outono e ciclos longos, aprendizado espiritual contínuo, períodos de 5 anos",
    amor: "Relacionamentos baseados em compromisso, casamento tradicional, união guiada por princípios morais",
    dinheiro: "Sucesso em carreiras acadêmicas, religiosas ou jurídicas, influência sobre grupos e comunidades",
    saude: "Saúde equilibrada, mas necessidade de atenção ao bem-estar espiritual e psicológico"
  },
  {
    arcano: 6,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_289/https://tarotfarm.com.br/wp-content/uploads/2020/12/Os-Enamorados-.jpg",
    nome: "Os Amantes",
    simNao: "Sim, mas com necessidade de escolha consciente",
    atributos: "Amor, união, beleza, prazer, lazer, conexões significativas",
    desafios: "Dúvidas, insegurança, irresponsabilidade, traição, leviandade",
    risco: "Sentimentalismo excessivo, fanatismo, ilusão nas relações",
    objetivo: "Dedicar-se de coração a um caminho, pessoa ou tarefa",
    tarefa: "Tomar decisões sinceras e espontâneas",
    arquetipo: "A encruzilhada",
    personalidade: "Indeciso, romântico, apaixonado, reflexivo",
    caracteristicasFisicas: "Atrativo, cativante, olhar expressivo",
    temporalidade: "Junho, influência de Gêmeos",
    amor: "Decisões importantes no amor, conexões fortes e desejo de harmonia",
    dinheiro: "Escolhas profissionais críticas, parcerias e contratos vantajosos",
    saude: "Equilíbrio entre corpo e mente, necessidade de alinhar sentimentos com ações"
  },
  {
    arcano: 7,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_285/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Carro-.jpg",
    nome: "O Carro",
    simNao: "Sim, desde que haja controle e direção",
    atributos: "Vontade, determinação, conquista, superação, sucesso",
    desafios: "Ansiedade, pressa, falta de consideração, impulsividade",
    risco: "Arrogância, descontrole emocional, agir sem planejamento",
    objetivo: "Experimentar o mundo, avançar para a vitória",
    tarefa: "Seguir em frente com disciplina e autocontrole",
    arquetipo: "A partida",
    personalidade: "Ambicioso, focado, competitivo, autoconfiante",
    caracteristicasFisicas: "Postura ereta, presença marcante, olhar determinado",
    temporalidade: "Julho, influência de Câncer",
    amor: "Movimento nos relacionamentos, necessidade de equilíbrio e diálogo",
    dinheiro: "Crescimento profissional acelerado, boas oportunidades financeiras",
    saude: "Energia intensa, necessidade de equilíbrio para evitar excesso de estresse"
  },
  {
    arcano: 8,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_278/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Forca-.jpg",
    nome: "A Força",
    simNao: "Sim, com paciência e domínio dos impulsos",
    atributos: "Coragem, autocontrole, compaixão, resistência",
    desafios: "Lidar com impulsos, superar medos internos, equilibrar força e gentileza",
    risco: "Perder o controle emocional, agir de forma agressiva ou dominadora",
    objetivo: "Dominar impulsos e alcançar vitórias sem violência",
    tarefa: "Enfrentar desafios com paciência e empatia",
    arquetipo: "A força interior",
    personalidade: "Forte, determinado, resiliente, bondoso",
    caracteristicasFisicas: "Expressão serena, corpo bem equilibrado e saudável",
    temporalidade: "Agosto, influência de Leão",
    amor: "Relações fortalecidas pela paciência e compreensão",
    dinheiro: "Êxito através da persistência, superação de desafios financeiros",
    saude: "Saúde forte, mas necessidade de evitar estresse emocional"
  },
{
    arcano: 9,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_288/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Eremita-.jpg",
    nome: "O Eremita",
    simNao: "Não, é necessário mais reflexão antes de agir",
    atributos: "Sabedoria, introspecção, paciência, solidão voluntária",
    desafios: "Isolamento excessivo, distanciamento, medo de pedir ajuda",
    risco: "Amargura, excentricidade, afastamento do mundo real",
    objetivo: "Autoconhecimento e busca pela verdade interior",
    tarefa: "Recolher-se para refletir e encontrar respostas",
    arquetipo: "O velho sábio",
    personalidade: "Reservado, introspectivo, observador, profundo",
    caracteristicasFisicas: "Aparência mais velha ou madura, olhar introspectivo",
    temporalidade: "Setembro, influência de Virgem",
    amor: "Momento de introspecção nas relações, necessidade de espaço",
    dinheiro: "Crescimento através da experiência e estudo, sucesso a longo prazo",
    saude: "Necessidade de descanso mental, busca por equilíbrio interior"
  },
  {
    arcano: 10,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_289/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Roda-da-Fortuna-.jpg",
    nome: "A Roda da Fortuna",
    simNao: "Sim, mas sujeito a mudanças inesperadas",
    atributos: "Movimento, oportunidades, progresso, elevação, desapego",
    desafios: "Ansiedade, perdas, instabilidade emocional e financeira",
    risco: "Fatalismo, falta de compreensão sobre a própria missão",
    objetivo: "Passar de um estado inferior para um superior, dominar a própria trajetória",
    tarefa: "Entender o necessário para cumprir a missão de vida",
    arquetipo: "A vocação, o destino",
    personalidade: "Adaptável, aceita mudanças com facilidade, vê oportunidades onde outros veem caos",
    caracteristicasFisicas: "Movimentação constante, expressão mutável",
    temporalidade: "Outubro, influência de Júpiter",
    amor: "Mudanças inesperadas nos relacionamentos, possibilidade de reviravoltas emocionantes",
    dinheiro: "Ciclos de alta e baixa, oportunidades inesperadas, necessidade de adaptação",
    saude: "Períodos de oscilação na saúde e bem-estar, aprendizado sobre aceitar a impermanência"
  },
  {
    arcano: 11,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_287/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Justica-.jpg",
    nome: "A Justiça",
    simNao: "Sim, mas apenas se houver equilíbrio e merecimento",
    atributos: "Inteligência, imparcialidade, justiça, merecimento, decisão",
    desafios: "Mau julgamento, frieza, distanciamento emocional, rigidez, inflexibilidade",
    risco: "Justiça própria, autoritarismo, preconceito",
    objetivo: "Responsabilidade pessoal, objetividade, honestidade e equilíbrio",
    tarefa: "Compreender as leis do mundo e fazer julgamentos sensatos, com coragem civil",
    arquetipo: "A busca pela verdade",
    personalidade: "Equilibrado, racional, exigente, ético, justo",
    caracteristicasFisicas: "Expressão séria, olhar observador, postura firme",
    temporalidade: "Setembro, influência de Libra",
    amor: "Relações baseadas em equilíbrio e honestidade, decisões importantes podem surgir",
    dinheiro: "Sucesso depende do merecimento e da honestidade, possibilidade de contratos e acordos",
    saude: "Busca pelo equilíbrio físico e emocional, necessidade de cuidar tanto do corpo quanto da mente"
  },
{
    arcano: 12,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_287/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Dependurado-.jpg",
    nome: "O Enforcado",
    simNao: "Não, a resposta requer paciência e reflexão",
    atributos: "Desenvolvimento à custa de muito esforço, idealismo, paciência, abnegação",
    desafios: "Sofrimento, sensação de abandono, longa espera, impotência diante do destino, bloqueios",
    risco: "Deixar-se pendurar, virar-se infinitamente em círculos",
    objetivo: "Crescimento na profundeza",
    tarefa: "Regresso, visão e disposição de fazer um sacrifício",
    arquetipo: "A prova",
    personalidade: "Reflexivo, resignado, visionário, místico",
    caracteristicasFisicas: "Postura introspectiva, olhar sereno, expressão de contemplação",
    temporalidade: "Novembro, influência de Netuno",
    amor: "Necessidade de paciência e compreensão, relações testadas pelo tempo",
    dinheiro: "Momento de pausa e sacrifício, possível estagnação financeira",
    saude: "Recomenda-se repouso e introspecção, possível necessidade de meditação e autoconhecimento"
  },
  {
    arcano: 13,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_284/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Morte-.jpg",
    nome: "A Morte",
    simNao: "Não, mas representa uma grande mudança necessária",
    atributos: "Transformação, reciclagem, renascimento, renovação, purificação",
    desafios: "Perdas, bloqueio total, impulsividade, ira, inconformidade, extremismo",
    risco: "Fingir de morto por medo, resistência à mudança",
    objetivo: "Solução, superação do ego, destruição de limites, mudança profunda",
    tarefa: "Despedida e descida ao inferno, recolhimento voluntário, encerrar algo, libertar-se",
    arquetipo: "A transformação",
    personalidade: "Intenso, reformador, desapegado, sábio",
    caracteristicasFisicas: "Olhar penetrante, traços marcantes, expressão séria",
    temporalidade: "Outubro/novembro, influência de Escorpião",
    amor: "Transformações inevitáveis, fim de ciclos, possibilidade de renascimento no amor",
    dinheiro: "Mudanças radicais na carreira, necessidade de reestruturação financeira",
    saude: "Processos de cura, regeneração física e emocional, libertação de padrões tóxicos"
  },
  {
    arcano: 14,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_291/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Temperaca-.jpg",
    nome: "A Temperança",
    simNao: "Sim, indica harmonia e equilíbrio. Sugere moderação e paciência.",
    atributos: "Equilíbrio, harmonia, serenidade, cura, integração, paciência, sabedoria, fluidez, espiritualidade.",
    desafios: "Dificuldade em encontrar equilíbrio, excessos, impaciência, estagnação, falta de moderação, superficialidade.",
    risco: "Perder-se na busca pela perfeição e não aceitar mudanças naturais.",
    objetivo: "Encontrar a harmonia interior e integrar aspectos opostos da vida.",
    tarefa: "Aceitar a orientação superior e encontrar a medida certa para cada situação.",
    arquetipo: "O condutor de almas.",
    personalidade: "Pessoa calma, centrada, mediadora e que sabe lidar com conflitos de forma diplomática.",
    caracteristicasFisicas: "Traços harmoniosos, aparência serena, olhar tranquilo, postura equilibrada.",
    temporalidade: "Período de transição estável, resolução gradual de situações. Pode indicar meses até um ano.",
    amor: "Relacionamentos equilibrados, maturidade emocional e disposição para compromissos saudáveis.",
    dinheiro: "Estabilidade financeira através de planejamento e controle emocional no ambiente de trabalho.",
    saude: "Saúde física e mental em harmonia, recuperação gradual, equilíbrio energético e espiritualidade"
  },
{
    arcano: 15,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_284/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Diabo-.jpg",
    nome: "O Diabo",
    simNao: "Não, indica aprisionamento a desejos e ilusões. Sugere desafios e manipulação.",
    atributos: "Desejo, paixão, ambição, poder, vícios, ilusões, materialismo, sedução, prazer, impulsividade, força criativa.",
    desafios: "Manipulação, obsessões, apegos tóxicos, autossabotagem, dominação, excesso de controle, fraqueza de caráter.",
    risco: "Ficar preso a padrões destrutivos, relacionamentos tóxicos e vícios sem perceber a própria responsabilidade.",
    objetivo: "Reconhecer as próprias sombras e libertar-se de influências negativas.",
    tarefa: "Superar os obstáculos interiores, tomar consciência das próprias limitações e buscar a liberdade.",
    arquetipo: "O adversário.",
    personalidade: "Pessoa intensa, magnética, sedutora, ambiciosa e com tendência ao controle ou manipulação.",
    caracteristicasFisicas: "Traços marcantes, aparência sensual, olhar penetrante, presença forte e carismática.",
    temporalidade: "Mudanças súbitas ou eventos que se repetem de forma cíclica. Pode indicar algo acontecendo em breve.",
    amor: "Relacionamentos passionais, mas com risco de obsessão e manipulação emocional.",
    dinheiro: "Sucesso profissional e financeiro, mas com riscos de ambição descontrolada e comportamentos antiéticos.",
    saude: "Cuidado com vícios, excessos e saúde mental. Pode indicar estresse ou problemas emocionais ocultos."
  },
  {
    arcano: 16,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_292/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Torre-.jpg",
    nome: "A Torre",
    simNao: "Não, indica rupturas e transformações drásticas. Sugere crises e mudanças inesperadas.",
    atributos: "Destruição, colapso, libertação, choque, recomeço, verdade revelada, renovação, ruína necessária, aprendizado forçado.",
    desafios: "Medo da mudança, resistência à verdade, orgulho ferido, perda repentina, crise de identidade, insegurança.",
    risco: "Apegar-se a estruturas que não se sustentam mais, negar a necessidade de mudança.",
    objetivo: "Romper com ilusões e reconstruir a vida sobre bases mais sólidas.",
    tarefa: "Explosão de limites estreitos, libertação de padrões destrutivos e aceitação do inesperado.",
    arquetipo: "A libertação.",
    personalidade: "Pessoa intensa, resistente a mudanças, que pode passar por reviravoltas significativas na vida.",
    caracteristicasFisicas: "Aparência impactante, olhar marcante, expressão séria ou preocupada, postura rígida.",
    temporalidade: "Eventos repentinos e imprevisíveis. Pode indicar mudanças drásticas a curto prazo.",
    amor: "Relacionamentos passando por crises ou transformações intensas. Possibilidade de rompimentos.",
    dinheiro: "Mudanças inesperadas no trabalho e na vida financeira, podendo indicar tanto perdas quanto novas oportunidades.",
    saude: "Problemas súbitos de saúde ou necessidade de reestruturação de hábitos e crenças."
  },
  {
    arcano: 17,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_289/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Estrela-.jpg",
    nome: "A Estrela",
    simNao: "Sim, simboliza esperança e renovação. Indica um futuro promissor.",
    atributos: "Beleza, brilho, renovação, revelação, expectativas realizadas, inspiração, conexão espiritual.",
    desafios: "Ingenuidade, futilidade, fragilidade, desperdício, idealização excessiva, falta de praticidade.",
    risco: "Perder-se em ilusões sobre o futuro e negligenciar o presente.",
    objetivo: "Entender os inter-relacionamentos maiores e obter o conhecimento da sabedoria do cosmos.",
    tarefa: "Criar esperança, desenvolver uma visão positiva para o futuro.",
    arquetipo: "Sabedoria.",
    personalidade: "Pessoa otimista, sonhadora, espiritualizada, com grande sensibilidade e fé no futuro.",
    caracteristicasFisicas: "Traços delicados, olhar esperançoso, expressão serena, postura aberta e receptiva.",
    temporalidade: "Período de renovação e esperança, podendo indicar meses até um ano.",
    amor: "Indica amor verdadeiro e relações harmoniosas, mas alerta contra expectativas irreais.",
    dinheiro: "Oportunidades de crescimento, mas necessidade de manter os pés no chão.",
    saude: "Equilíbrio emocional e espiritualidade em ascensão, ótima para recuperação e bem-estar."
  },
{
    arcano: 18,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_282/https://tarotfarm.com.br/wp-content/uploads/2020/12/A-Lua-.jpg",
    nome: "A Lua",
    simNao: "Não, indica ilusões e incertezas. Sugere enganos e desafios emocionais.",
    atributos: "Feminilidade, fecundidade, intuição, mistério, sonhos, emoções profundas, criatividade.",
    desafios: "Ilusão, enganos, traições, inimigos ocultos, frustrações, insegurança, confusão emocional.",
    risco: "Superar medos e evitar tomar decisões impulsivas com base em ilusões.",
    objetivo: "Regresso à luz, encontrar clareza e verdade além das ilusões.",
    tarefa: "Enfrentar os próprios medos e incertezas para alcançar a verdade interior.",
    arquetipo: "A noite, a alvorada.",
    personalidade: "Pessoa sensível, intuitiva, misteriosa, com tendência ao devaneio ou à indecisão.",
    caracteristicasFisicas: "Traços delicados, olhar enigmático, presença envolvente, movimentos suaves e fluidos.",
    temporalidade: "Eventos noturnos ou períodos de confusão emocional. Pode representar ciclos lunares.",
    amor: "Relacionamentos marcados por mistério e emoções intensas, com riscos de ilusões e traições.",
    dinheiro: "Situações obscuras nos negócios e necessidade de evitar riscos.",
    saude: "Sensibilidade emocional elevada, propensão a crises psicológicas ou visões espirituais."
  },
  {
    arcano: 19,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_289/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Sol-.jpg",
    nome: "O Sol",
    simNao: "Sim, representa sucesso e felicidade. Indica realizações e clareza.",
    atributos: "Alegria, brilho pessoal, realização, vitalidade, sucesso, expansão, otimismo.",
    desafios: "Orgulho, arrogância, vaidade, egoísmo, excesso de confiança.",
    risco: "Excesso de otimismo pode levar à negligência de riscos e problemas reais.",
    objetivo: "Novo nascimento, percepção sábia e humildade madura.",
    tarefa: "Praticar a verdadeira reconciliação com a própria essência e com os outros.",
    arquetipo: "O Pai cósmico, o dia.",
    personalidade: "Pessoa carismática, vibrante, extrovertida e otimista, com grande autoconfiança.",
    caracteristicasFisicas: "Traços radiantes, sorriso marcante, postura segura e envolvente.",
    temporalidade: "Eventos felizes e bem-sucedidos. Pode indicar o verão ou períodos ensolarados.",
    amor: "Relacionamentos felizes, harmônicos e com grande cumplicidade e alegria.",
    dinheiro: "Êxito nos negócios e reconhecimento profissional. Expansão e prosperidade.",
    saude: "Boa saúde, energia vital em alta, excelente para práticas ao ar livre e bem-estar físico."
  },
  {
    arcano: 20,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_289/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Jugamento-.jpg",
    nome: "O Julgamento",
    simNao: "Sim, simboliza renascimento e transformação. Indica um chamado para mudanças profundas.",
    atributos: "Novidades, ajuda, oportunidades, melhora, cura, proteção, avaliação, despertar espiritual.",
    desafios: "Insegurança, apego ao passado, indecisão, atrasos, resistência à transformação.",
    risco: "Ficar preso a arrependimentos e não aproveitar as oportunidades de renovação.",
    objetivo: "Cura e libertação dos erros do passado para recomeçar com sabedoria.",
    tarefa: "Aceitar as mudanças inevitáveis e ouvir o chamado para um novo propósito.",
    arquetipo: "O milagre da transformação.",
    personalidade: "Pessoa que passou por grandes desafios e encontrou força na renovação. Alguém que inspira mudanças.",
    caracteristicasFisicas: "Traços marcantes, olhar expressivo, postura decidida, ar de resiliência.",
    temporalidade: "Eventos rápidos, decisões importantes, mudanças iminentes. Pode indicar semanas.",
    amor: "Relacionamentos renascidos, reconciliações ou decisões definitivas no amor.",
    dinheiro: "Oportunidades inesperadas de trabalho e crescimento profissional após períodos difíceis.",
    saude: "Regeneração física e emocional. Possibilidade de recuperação e novos começos."
  },
  {
    arcano: 21,
    imagem: "https://sp-ao.shortpixel.ai/client/to_auto,q_lossy,ret_img,w_287/https://tarotfarm.com.br/wp-content/uploads/2020/12/O-Mundo-.jpg",
    nome: "O Mundo",
    simNao: "Sim, representa sucesso e plenitude. Indica a conclusão bem-sucedida de um ciclo.",
    atributos: "Realização, êxito, abertura, reencontro, poder, transcendência, totalidade, expansão.",
    desafios: "Sobrecarga, pessimismo, cansaço, medo de avançar para novas experiências.",
    risco: "Achar que o ciclo está completo quando ainda há mais a aprender e explorar.",
    objetivo: "Chegar ao ponto máximo de realização e começar uma nova jornada com consciência.",
    tarefa: "Aceitar o próprio destino e compreender a conexão entre todas as coisas.",
    arquetipo: "O reencontro do paraíso.",
    personalidade: "Pessoa confiante, realizada, experiente e segura de si, que conquistou grandes metas.",
    caracteristicasFisicas: "Postura ereta, olhar sereno, presença forte e marcante, expressão de satisfação.",
    temporalidade: "Período de colheita e recompensa. Pode indicar anos ou o fim de uma longa jornada.",
    amor: "Relacionamentos maduros e completos. Felicidade e estabilidade amorosa.",
    dinheiro: "Sucesso profissional e reconhecimento. Fase de crescimento e conquistas materiais.",
    saude: "Saúde equilibrada e vitalidade plena. Bem-estar físico, emocional e espiritual."
  }
    ];

    function sortearCarta() {
    const carta = cartas[Math.floor(Math.random() * cartas.length)];
    const resultado = document.getElementById("resultado");
    resultado.innerHTML = `
        <img src="${carta.imagem}" style="width:350px; border-radius:8px;">
        <div style="flex:1;">

        <h2 style="text-align:left;">${carta.nome}</h2>
        <p><strong>Sim ou Não:</strong> ${carta.simNao}</p>
        <p><strong>Atributos:</strong> ${carta.atributos}</p>
        <p><strong>Desafios:</strong> ${carta.desafios}</p>
        <p><strong>Personalidade:</strong> ${carta.personalidade}</p>
        <p><strong>Características Físicas:</strong> ${carta.caracteristicasFisicas}</p>
        <p><strong>Temporalidade:</strong> ${carta.temporalidade}</p>
        <p><strong>Amor e Relacionamentos:</strong> ${carta.amor}</p>
        <p><strong>Dinheiro e Trabalho:</strong> ${carta.dinheiro}</p>
        <p><strong>Saúde e Espiritualidade:</strong> ${carta.saude}</p>
    `;
    resultado.style.display = "flex";
}
</script>

</body>
</html>
