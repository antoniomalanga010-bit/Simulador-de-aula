# Simulador de Aula — versão 15 (Matemática expandida)

## Estado actual do projecto

O projecto reúne 10 disciplinas e 36 temas, com aulas em JSON, exercícios resolvidos, ilustrações locais, testes por tema e uso offline via service worker. Para executar, extrai o ZIP e abre a pasta num servidor local ou HTTPS; não abras a aplicação directamente por `file://`.

- Interface responsiva, menu lateral recolhível, modo claro/escuro e pesquisa global.
- Aulas, testes e ilustrações de todas as disciplinas incluídas no catálogo.
- Página Testes com simulado geral, selecção por disciplina/tema, filtros de dificuldade, quantidade configurável, prática guiada e modo de avaliação.
- Em cada tentativa: opções em linhas separadas, ordenação aleatória, barra de progresso, mapa de perguntas, marcação para rever, navegação, temporizador opcional e gravação automática.
- Resultado detalhado com acertos, erros, respostas em branco, duração, decomposição por tema, correcção explicada, repetição dos erros, caderno de erros, histórico, exportação JSON e impressão/guardar PDF.
- As tentativas interrompidas podem ser retomadas; iniciar um novo teste pergunta antes de substituir uma tentativa guardada.
- Os bancos de escolha múltipla foram revistos para remover variantes que apenas mudavam valores numéricos, manter pelo menos 40 perguntas por tema e distribuir a posição da resposta correcta. O total actual é de **1 511 perguntas em 36 bancos**.
- Os recursos usados pela aplicação, incluindo folhas de estilo e bancos de perguntas, funcionam localmente; referências de estudo externas exigem Internet.

## Como executar no Windows
1. Extrai o ZIP para uma pasta, por exemplo `C:\Projetos\simulador-de-aula`.
2. Abre a pasta no Visual Studio Code.
3. Inicia um servidor local: com Live Server, clica com o botão direito em `index.html` e escolhe **Open with Live Server**; alternativamente executa `python -m http.server 8000` no terminal dessa pasta.
4. Abre `http://localhost:8000` no navegador.
5. Para instalar como PWA, abre a aplicação em HTTPS ou localhost e usa a opção de instalação apresentada pelo navegador. Para testar o uso offline, abre primeiro a aplicação online e depois desliga a ligação nas ferramentas do navegador.

**Não abras `index.html` com duplo clique (`file://`)**: os ficheiros JSON e o service worker precisam de um servidor local para funcionarem correctamente.

## Dados e privacidade

Os resultados, as perguntas vistas recentemente, o caderno de erros e a tentativa activa são guardados em `localStorage` nesse navegador/dispositivo. Não são enviados para um servidor pela aplicação. Limpar os dados do navegador elimina estes registos. O histórico de notas pode ser apagado na página Meu desempenho; o caderno de erros é mantido quando se limpa apenas o histórico.

## Atualização v3 — Matemática

- O catálogo de Matemática agora apresenta apenas **Função** e **Progressão Aritmética (P.A.)**. Os quatro temas separados de domínio, imagem e pares ordenados foram removidos do catálogo porque esses conteúdos estão integrados na aula de Função.
- A nova aula `assets/data/topics/matematica/progressao-aritmetica.json` inclui 13 secções, exemplos resolvidos, tabela e gráfico discreto, resumo de fórmulas, lista de verificação e 30 exercícios com respostas explicadas.
- O service worker foi actualizado para incluir a nova aula offline.


## Conteúdos de Contabilidade integrados

A disciplina Contabilidade inclui agora as aulas completas **Operações com compras** e **Operações com vendas**, com 13 e 12 secções, respectivamente, exemplos resolvidos e 20 exercícios por tema. Os bancos de compras e vendas foram revistos para reduzir enunciados que apenas mudavam os valores numéricos; na versão de testes actual contêm 84 e 56 perguntas distintas por modelo, respectivamente, integradas na área Testes e no cache offline.

Nota pedagógica: os lançamentos são apresentados como esquemas; os códigos de contas devem seguir o plano de contas adoptado na escola. As taxas e o tratamento fiscal de operações reais devem ser confirmados na legislação angolana em vigor e junto da AGT.


## Actualização v5 — Electrotecnia

O catálogo de Electrotecnia contém agora exactamente dois temas: **Introdução à Electrotecnia** e **Componentes electrónicos**. O antigo item “Registor electrónico” foi incorporado no estudo dos resistores dentro de Componentes electrónicos.

- Aulas em JSON com explicações, fórmulas, tabelas, exemplos resolvidos e exercícios com respostas.
- Ilustrações SVG locais e responsivas para resistor, potenciómetro, condensador, indutor, díodo/LED, transístor, circuito integrado e circuitos de medição.
- Bancos com perguntas de escolha múltipla por tema, ligados ao selector da área Testes.
- Pesquisa indexa secções e exercícios das aulas disponíveis.
- Laboratório básico da Lei de Ohm adicionado para Electrotecnia.
- Os novos ficheiros e imagens estão incluídos na shell offline do service worker.

As imagens são esquemas didácticos originais; para ligação real, confirma sempre a referência, o pinout e o datasheet do fabricante. As experiências devem usar fonte isolada de baixa tensão e ser supervisionadas.


## Versão 7 — Química completa

A disciplina Química foi reorganizada em exactamente três temas: (1) Reações químicas e equações químicas, reunindo acerto de equações e Lei de Lavoisier; (2) Coeficiente estequiométrico; e (3) Estado físico. Cada tema tem matéria em JSON, 25 exercícios com soluções e um banco próprio de perguntas de escolha múltipla. As ilustrações SVG são locais e incluídas no modo offline.


## Actualização TLP — dois temas completos

- **Programação orientada a objectos**: fundamentos, variáveis, tipos, classes, objectos, abstracção, encapsulamento, propriedades get/set, herança, polimorfismo, interfaces, consola e validação.
- **Algoritmos, estruturas de controlo e modularização**: pseudocódigo, fluxogramas, selecção, ciclos, métodos, arrays, listas, pesquisa, validação, testes e depuração.
- Cada tema contém 18/19 secções de estudo, 30 exercícios resolvidos, um banco com 40 perguntas e ilustrações SVG locais.
- Para funcionamento offline, os JSON e SVG de TLP foram adicionados ao `APP_SHELL`; o cache foi actualizado para `simulador-aula-v8-tlp`.
- Os exemplos de linguagem usam C# como referência, por causa dos conceitos Console Application e get/set.


## Conteúdos novos — Língua Portuguesa

A disciplina tem agora três temas completos: **Classes de Palavras**, **Análise Sintáctica** e **Estudo do Texto**. Cada aula inclui explicações, exemplos, ilustrações SVG locais, exercícios com respostas explicadas, checklist e referências gratuitas. Cada banco de testes contém 40 perguntas de escolha múltipla com quatro opções e feedback. Os recursos foram adicionados ao catálogo e ao pré-carregamento do modo offline.

A terminologia sintáctica pode variar entre gramáticas escolares tradicionais e actuais; para avaliações, segue a nomenclatura utilizada no programa da escola.


## Actualização SEAC — versão 9

A disciplina SEAC passou a ter exactamente dois temas completos: **Comutação** e **Introdução a Redes de Computadores**. Foram adicionados dois ficheiros de aula JSON, dois bancos de avaliação com 40 perguntas cada e dez ilustrações SVG locais. O service worker foi actualizado para `simulador-aula-v10-seac` e inclui os novos recursos no pacote de utilização offline. Na terminologia de redes, foi interpretado o “PAW” da nota original como **PAN (Personal Area Network)**, que é a sigla comum para rede de área pessoal.


## Actualização v11 — Desenho Técnico

A disciplina Desenho Técnico foi desenvolvida com três temas: Introdução ao Desenho Técnico; Tipos de Desenho Técnico, Instrumentos e Materiais; Tipos de Linha. Cada tema contém 18–20 secções, 30 exercícios resolvidos, 40 perguntas de avaliação e ilustrações SVG guardadas localmente. O service worker foi actualizado para incluir as novas aulas, os bancos de testes e os SVG.


## FAI — Formação de Atitudes Integradoras (versão 12)

A disciplina FAI foi desenvolvida em cinco aulas completas, mantendo os identificadores dos temas existentes para preservar os endereços internos:

1. A qualidade de vida e a preservação da natureza.
2. O património local e a sua conservação.
3. A chuva: sua importância e consequências.
4. O aquecimento global e as mudanças climáticas.
5. O encontro com a natureza: a poluição.

Cada aula reúne 15–16 secções, exemplos, tabelas, ilustrações SVG locais, 30 exercícios resolvidos, uma lista de revisão e referências gratuitas. Cada tema tem um banco com 40 perguntas de escolha múltipla e explicações. Os novos JSON e SVG estão incluídos no cache inicial do service worker para uso offline.


## Empreendedorismo — versão 12

A disciplina Empreendedorismo está organizada em dois temas completos: **Ética perante os clientes** (16 secções, 30 exercícios resolvidos e 40 perguntas de avaliação) e **Gestão de marketing** (18 secções, 30 exercícios resolvidos e 40 perguntas de avaliação). Foram incluídos diagramas SVG locais e os novos recursos no cache offline.

As matérias usam exemplos de pequenos negócios no contexto angolano. Para decisões legais, fiscais ou comerciais reais, confirme sempre a legislação aplicável e os canais oficiais.


## Página Testes — versão 15

A página Testes permite criar uma avaliação por tema, por disciplina (todos os temas) ou um simulado geral. Todos os 26 temas do catálogo possuem banco de perguntas validado, num total de 1 111 perguntas após a remoção de variantes repetitivas. O motor permite filtrar por dificuldade, escolher a quantidade de perguntas, usar o modo de prática guiada ou modo de avaliação, definir um limite de tempo, navegar pelo mapa de perguntas, marcar questões para rever, retomar uma tentativa guardada, rever cada resposta com explicação, refazer erros e exportar/imprimir o relatório. As perguntas vistas recentemente são evitadas quando existem alternativas suficientes; cada tentativa usa perguntas únicas e as opções aparecem verticalmente com a ordem baralhada. Iniciar um novo teste pede confirmação se existir uma tentativa interrompida, para evitar perda acidental. O filtro de dificuldade normaliza as designações usadas nos bancos. O caderno de erros e o histórico são guardados localmente no navegador.


## Laboratórios interactivos — versão 16

A página **Laboratórios** foi ampliada para abranger todos os 26 temas das 10 disciplinas do catálogo. Cada tema tem uma actividade própria — não apenas um simulador genérico — com controlos, resultados dinâmicos, uma missão e uma dica de aprendizagem. Exemplos: gráficos de funções e progressões aritméticas; cálculo de compras/vendas; Lei de Ohm e dimensionamento teórico de resistência para LED; classificação gramatical e análise de frases; execução ilustrativa de algoritmos; acerto de equações e estequiometria; comutação e topologias de rede; escalas e tipos de linha; dilemas de atendimento e cálculo de marketing; património local, captação de chuva, clima e poluição.

- **Exploração e navegação:** selector de disciplina e tema, catálogo pesquisável com 26 entradas, opção “Surpreende-me” e “Continuar a explorar”.
- **Aprendizagem activa:** 3 perguntas por tema (78 no total), opções baralhadas, resposta explicada imediatamente, próxima pergunta, resultado final e repetição do desafio.
- **Motivação:** XP, distintivos, contagem de experiências, temas visitados e temas dominados. Os prémios por pergunta e por primeira exploração não são repetidos indefinidamente.
- **Reflexão e continuidade:** observações guardadas por tema no navegador, registo de experiências após interagir com uma actividade, retoma do último tema e exportação do diário de laboratório em JSON.
- **Inventário de património:** registo local de bens materiais, naturais e imateriais, limitado a 100 registos para evitar crescimento ilimitado dos dados locais.
- **Privacidade e funcionamento:** o diário, a pontuação e as reflexões ficam no `localStorage` do navegador e não são enviados pela aplicação para um servidor. O service worker utiliza o cache `simulador-aula-v16-laboratorios-interactivos`; os ficheiros visuais dos laboratórios são SVG/HTML/CSS locais, sem dependência de imagens externas.
- **Limites didácticos:** os cálculos fiscais, as estimativas de marketing e clima e os modelos de partículas são simplificações para estudo, não aconselhamento profissional nem medições reais. Os exercícios eléctricos são simulações de baixa tensão; não autorizam trabalho na rede eléctrica. O código de POO é apresentado como exemplo de leitura e não é executado no servidor.

A validação desta versão percorreu os 26 módulos e os 78 itens de desafio, accionou os controlos específicos, verificou cálculos de P.A., captação de chuva, escala de desenho, estequiometria e compras, confirmou a persistência de reflexões/inventário e a exportação do diário, testou a barreira do simulador LED para uma fonte insuficiente, e executou verificações responsivas em Chromium. Não foram observados erros JavaScript ou erros de consola durante esses fluxos; a renderização visual foi revista por captura de ecrã.


## Actualização v15 — Matemática expandida e integrada

A disciplina Matemática passa a conter 12 temas, nesta ordem:

1. Teoria de Conjuntos;
2. Números Inteiros Relativos e Racionais;
3. Operações Fundamentais, Potências, m.d.c. e m.m.c.;
4. Introdução às Equações do 1.º Grau e Geometria Plana;
5. Monómios e Polinómios;
6. Casos Notáveis da Multiplicação e Decomposição em Factores;
7. Equações e Inequações do 1.º Grau e Sistemas;
8. Teorema de Pitágoras e Áreas de Figuras Planas;
9. Números Reais e Radiciação;
10. Equações do 2.º Grau, fórmula de Bhaskara e discriminante Δ;
11. Função (conteúdo anterior preservado);
12. Progressão Aritmética (P.A., conteúdo anterior preservado).

Cada um dos dez novos temas tem 12 secções teóricas, 20 exercícios resolvidos e 40 perguntas de escolha múltipla com quatro opções, resposta correcta identificada e explicação. Foram adicionados 11 diagramas SVG e dez laboratórios interactivos próprios, ligados a Aulas, Testes e Meu desempenho pelos identificadores de tema. O catálogo geral reúne 36 temas e 1 511 perguntas em 36 bancos.

O service worker foi actualizado para `simulador-aula-v17-matematica-ampliada` e inclui as novas aulas, bancos e ilustrações no conjunto de recursos offline.

Nota de utilização: executar em `localhost` ou HTTPS, não directamente através de `file://`. Antes da publicação, testar as páginas no servidor utilizado pelo site e limpar/recarregar o cache antigo se o navegador ainda apresentar a versão anterior.


## Versão 18 — desempenho e Matemática ampliada

- Página Meu desempenho reforçada com cobertura de temas, volume de perguntas, variação recente e sugestões de revisão pelos temas com menor média.
- Matemática passa a incluir cinco novos temas: Introdução à Estatística; Lógica Matemática; Álgebra Avançada; Trigonometria; Funções Quadráticas, Exponenciais e Logarítmicas.
- Cada novo tema inclui aula JSON, 20 exercícios orientados, banco de 40 perguntas, diagrama SVG e actividade/desafio de laboratório.
- Os resultados continuam guardados localmente no navegador; não existe sincronização automática entre dispositivos.


## Física (versão v20)

A disciplina Física inclui seis temas introdutórios, aulas com 12 secções por tema, 10 exercícios de consolidação por aula, 20 perguntas de escolha múltipla por tema e 18 ilustrações SVG optimizadas para a Web. Os seis laboratórios incluem conversões de unidades, apoio à medição, investigação científica, mudanças de estado, referenciais e cálculo de MRU. Os ficheiros da disciplina estão em `assets/data/topics/fisica/`, `assets/data/quizzes/fisica/` e `assets/images/fisica/`.


## Física — expansão v20

Foram acrescentados seis temas: Forças e suas Interacções/Leis de Newton; Peso, Atrito e Força Elástica; Trabalho Mecânico e Potência; Energia Mecânica; Princípio da Conservação da Energia; Calor e Temperatura. Cada tema inclui 12 secções, 10 exercícios com respostas, 20 perguntas de escolha múltipla e três ilustrações SVG. Os seis temas têm laboratórios interactivos e os recursos foram incluídos no service worker.
