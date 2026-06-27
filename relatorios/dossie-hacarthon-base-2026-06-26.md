# Dossie haCARthon - base consolidada

Atualizado em: 2026-06-26
Objetivo: consolidar o que os materiais recentes do haCARthon mostram sobre desafio, personas, metodo, pitch e ambiente de teste do CAR.

## Fontes lidas

- `C:\Users\Rubin\Downloads\Hacarthon - Live de Pitch (2).pdf`
- `C:\Users\Rubin\Downloads\ideacao_prototipacao.pdf`
- `C:\Users\Rubin\Downloads\Identificacao_oportunidades.pdf`
- `C:\Users\Rubin\Downloads\Acesso ao Módulo de Cadastro Pré- Preenchido.pdf`
- `C:\Users\Rubin\Downloads\tour-meu-imovel-rural-final.mp4`

Observacao sobre o video:
- O arquivo de video foi identificado no ambiente local, mas nesta rodada a consolidacao ficou baseada principalmente nos PDFs e no material operacional ja extraido do ambiente de testes.

## 1. Leitura rapida do haCARthon

O haCARthon quer solucoes inovadoras para fortalecer o SICAR e consolidar o CAR como Bem Publico Digital.

Os 3 desafios centrais apresentados nos materiais sao:

1. Simplificar o CAR para o usuario.
2. Melhorar o acesso a dados geoespaciais do CAR.
3. Aumentar o entendimento das legislacoes do CAR.

O recado mais repetido nos materiais e direto:
- comece pelo problema, nao pela solucao;
- use o que o governo ja construiu antes de propor algo novo;
- observe a jornada real do usuario;
- escolha uma dor pequena, clara e demonstravel.

## 2. Personas mais fortes do material

### Seu Raimundo

Perfil:
- pequeno ou medio produtor rural;
- depende da propriedade para renda e estabilidade da familia.

Ganhos esperados:
- regularizacao sem advogado;
- acesso a credito rural verde;
- resolver pelo celular.

Dores:
- internet instavel;
- depende de outras pessoas para conseguir usar o sistema;
- linguagem tecnica;
- medo de errar e perder o cadastro.

### Luana

Perfil:
- analista ambiental do orgao estadual;
- cuida da fila de validacao de cadastros.

Ganhos esperados:
- pre-validacao automatizada;
- dados integrados num painel unico;
- templates inteligentes de parecer.

Dores:
- fila enorme de analises pendentes;
- sobreposicoes dificeis de detectar;
- troca de aba entre varios sistemas.

## 3. Onde os materiais dizem que mora a oportunidade

Pontos de dor destacados:
- informacao dispersa e linguagem tecnica inacessivel;
- custo alto e dependencia de terceiros para georreferenciamento;
- falta de notificacao proativa;
- feedback confuso sobre o que corrigir, como corrigir e ate quando;
- dificuldade com legislacao;
- dificuldade com validacao e com exportacao de dados.

Filtro pratico para recortar oportunidade:

1. Para qual persona?
2. Em qual etapa da jornada?
3. Qual dor exata sera resolvida?
4. Isso ja existe em alguma plataforma atual?
5. Qual e a menor entrega que prova valor?

## 4. Metodo de ideacao e prototipacao recomendado

Os materiais empurram o time para um caminho simples:

### Descobrir
- conhecer usuario, dor, contexto e o que ja existe;
- usar plataformas reais como usuario;
- anotar atrito, confusao e travamento;
- pesquisar dados, repositorios, codigos e documentacoes.

Ferramentas sugeridas:
- brainstorming;
- matriz CSD;
- desk research;
- persona;
- mapa de empatia;
- um dia na vida;
- analise do ecossistema.

### Definir
- sintetizar desafio, usuario, dor e proposta de valor;
- mapear jornada;
- usar Jobs to Be Done;
- agrupar padroes de dor;
- identificar `opportunity gaps`.

### Desenvolver
- abrir varias solucoes para o mesmo problema;
- usar `How Might We`;
- buscar analogias em outros mercados;
- comparar com benchmarks;
- usar `SCAMPER`.

### Entregar
- priorizar o que cabe no tempo;
- validar com usuario real quando possivel;
- sair com um prototipo pronto para o pitch.

Ferramentas de priorizacao destacadas:
- matriz RICE;
- matriz impacto x esforco.

Regra importante do material:
- se nao cabe em 48h com o time, provavelmente esta grande demais para o hackathon.

## 5. Ideias-forca que os materiais praticamente sugerem

Os exemplos empurram muito para uma linha de solucao como esta:
- jornada guiada;
- linguagem simples;
- checklist;
- pre-preenchimento;
- notificacoes claras;
- reducao de erro antes do envio;
- celular como canal principal.

Exemplo forte do material:
- QR code no comunicado;
- entrada simples no celular;
- mapa pre-preenchido;
- checklist em linguagem simples;
- envio com protocolo;
- acompanhamento por notificacao.

Isso combina muito com o desafio 1 e tambem encosta no desafio 3.

## 6. Estrutura de pitch recomendada

O PDF de pitch traz uma estrutura de 9 blocos:

1. Introducao
2. Problema
3. Solucao
4. Como funciona
5. Diferenciais
6. Impacto esperado
7. Time
8. Proximos passos ou pedido para viabilizar
9. Encerramento

Perguntas-chave que o pitch precisa responder:
- qual problema do CAR foi identificado?
- quem sofre com esse problema?
- por que ele importa?
- o que e a solucao?
- como ela funciona na jornada real?
- o que a torna diferente do que existe hoje?
- o que melhora para usuario, governo e CAR?
- o que seria necessario para implementar?

Orientacao importante do proprio material:
- usar imagens, telas, wireframes e prototipo na parte `como funciona`.

Frase-resumo usada no material:
- `[nome da solucao] e uma/um [tipo de solucao] que ajuda [publico-alvo] a resolver [problema] por meio de [diferencial ou funcionamento].`

Exemplo mostrado:
- `CAR Facil` como assistente digital para preencher e retificar o CAR com linguagem simples e alertas antes do envio.

## 7. Ambiente de teste do CAR

O PDF do modulo pre-preenchido traz orientacoes operacionais importantes:

### Links do ambiente de teste

- baixar/acessar modulo: `https://car-sus.dataprev.gov.br/#/baixar`
- enviar cadastro: `https://car-sus.dataprev.gov.br/#/enviar`
- central do proprietario/possuidor: `https://car-sus.dataprev.gov.br/#/central/acesso`

### Regras operacionais

- usar exclusivamente o ambiente de testes;
- nao enviar no ambiente oficial de producao do SICAR;
- o modulo offline usa o mesmo ponto de entrada;
- a associacao com o SNCR esta obrigatoria no cadastro offline.

### Credenciais de teste registradas no PDF

Opcao 1:
- CPF: `10728210100`
- senha: `!Carteira6`
- data de nascimento: `12/12/2002`

Opcao 2:
- CPF: `28701615491`
- senha: `!Carteira6`
- data de nascimento: `01/01/1980`

### Codigos SNCR do PDF

Para o CPF `10728210100`:
- `9130730239223`
- `9130730254613`

Para o CPF `28701615491`:
- `2420200634280`
- `2480450028362`
- `9500339031245`
- `9500339031326`
- `9501737335390`

## 8. Leitura pragmatica para o time hoje

Se a meta for decidir rumo rapido hoje, a base consolidada aponta isto:

1. O caminho mais natural e forte continua sendo simplificar o CAR para o usuario.
2. A persona mais forte para demo e narrativa continua sendo o Seu Raimundo.
3. A menor entrega com boa cara de valor e uma jornada guiada com linguagem simples e prevencao de erro.
4. O pitch precisa mostrar problema real, jornada, diferenciais e impacto, nao so interface bonita.
5. Vale usar o ambiente de teste do CAR para observar friccao real e transformar isso em evidencia do problema.

## 9. Hipoteses de MVP que esta base favorece

- assistente guiado para declaracao ou retificacao;
- checklist de pendencias em linguagem simples;
- explicador de legislacao com contexto do campo;
- alerta de inconsistencias antes do envio;
- acompanhamento simples de status e proximos passos;
- funil de triagem para dizer `o que fazer agora` sem jogar o usuario em varias telas.

## 10. Proximo uso recomendado desta base

Esta base serve para:
- briefing do time;
- definicao de recorte do MVP;
- roteiro de pitch;
- preparacao de prototipo;
- observacao da jornada real no ambiente de testes.
