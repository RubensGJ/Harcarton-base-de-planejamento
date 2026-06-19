# Fontes da avaliacao do GeoRascunho CAR

Data da avaliacao: 18/06/2026

## Decisao analisada

Avaliar se o escopo `escopo_geoRascunho_CAR.docx` tem mercado, e viavel, atende ao haCARthon, cumpre os requisitos e tem chance competitiva real.

## Fontes locais revisadas

1. `escopo_geoRascunho_CAR.docx`, 6 paginas. Documento original preservado; texto, tabelas, cabecalhos e rodapes foram extraidos. Nao ha comentarios nem alteracoes controladas.
2. `haCARthon - Briefing dos desafios - versao 2.pdf`, 16 paginas. Fonte mais recente para desafios, personas, exemplos de solucao e regra de codigo aberto.
3. `haCARthon - Briefing dos desafios.pdf`, 15 paginas. Comparado com a versao 2 para identificar mudancas.
4. `haCARthon - Guia do Participante.pdf`, 7 paginas. Fonte principal para entregas, video de prototipo e criterios de avaliacao.
5. `Edital haCARthon - Assinado - SEI_0993344_Edital_158.pdf`, 7 paginas. Fonte formal para elegibilidade, submissao, julgamento, propriedade intelectual e eliminacao.
6. `Cronograma Edital haCARthon - enviado a Presidencia.pdf`, 1 pagina. Fonte de prazos.
7. `TranscricaoVideo1 (1).txt`, live preparatoria. Fonte nova para orientacoes operacionais, independencia de plataforma, ausencia de API publica e recorte de MVP.
8. `links uteis.txt`. Inventario com 47 URLs unicas, lido integralmente para roteamento da pesquisa.
9. `pesquisa-ferramentas-agentes-haCARthon.md` e `.agents/`. Usados como contexto interno, sem substituir fontes oficiais.

## Paginas locais decisivas

- Briefing v2, paginas 10 a 12: o Desafio 2 trata de atualizar anualmente, com rapidez e acuracia, o uso e cobertura do solo; cita bases integradas, vetorizacao, geracao automatizada e desenho georreferenciado acessivel.
- Briefing v2, paginas 5 e 6: Raimundo e Luana.
- Briefing v2, paginas 9, 12, 15 e 16: nao e obrigatorio entregar software funcional, mas a solucao deve poder evoluir em modelo de codigo aberto.
- Guia, pagina 5: ideacao, video de prototipo de ate 2 minutos e pitch.
- Guia, pagina 6: pertinencia, relevancia, usabilidade/design e inovacao/criatividade; inovacao desempata.
- Edital, pagina 3: video de ate 3 minutos e eliminacao por entrega incompleta, ausente ou fora do prazo.
- Transcricao da live: recomenda uma persona, uma etapa, uma dor e a menor entrega que prove valor em 48 horas; o prototipo deve ser independente de ArcGIS ou Google Earth Engine; dados publicos do CAR podem ser baixados, mas as APIs ainda nao sao publicas.

## Conflitos resolvidos

1. Video: o edital admite 3 minutos, mas o Guia rejeita videos acima de 2 minutos. Foi adotado o limite conservador de 2 minutos.
2. Codigo: o briefing antigo dizia que todas as solucoes deveriam ser desenvolvidas em codigo aberto. A versao 2 esclarece que elas devem ser pensadas para desenvolvimento e evolucao aberta; software funcional e codigo-fonte nao sao obrigatorios na avaliacao.
3. APIs do CAR: a Consulta Publica permite mapas e downloads, mas a live informa que as APIs de dados do CAR ainda sao restritas a orgaos de governo. O parecer nao assume integracao por API publica.
4. SNCR/CCIR: o escopo generaliza uma exigencia identificada no SICAR/PA como se fosse nacional. A avaliacao trata essa afirmacao como nao comprovada para todo o Brasil.

## Fontes web acessadas em 18/06/2026

### Oficiais e primarias

- Servico oficial do CAR: https://www.gov.br/pt-br/servicos/inscrever-imovel-rural-no-cadastro-ambiental-rural-car
- Nova Consulta Publica do CAR: https://www.gov.br/gestao/pt-br/assuntos/noticias/2026/maio/mgi-lanca-nova-plataforma-de-consulta-a-dados-publicos-do-car
- CAR como Bem Publico Digital e modulo pre-preenchido: https://www.gov.br/governodigital/pt-br/noticias/na-cop30-mgi-lanca-o-car-como-primeiro-bem-publico-digital-do-governo-brasileiro
- Consulta Publica: https://consulta.car.gov.br/about
- Lei 12.651/2012: https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2012/lei/l12651compilado.htm
- Decreto 7.830/2012: https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2012/decreto/d7830.htm
- MapBiomas Colecoes: https://brasil.mapbiomas.org/colecoes-mapbiomas/
- Painel da Regularizacao Ambiental: https://www.gov.br/florestal/pt-br/assuntos/regularizacao-ambiental/painel-regularizacao

### Benchmark de mercado

- MAPADOCAR: https://www.mapadocar.com.br/sobre.html
- Registro Rural: https://www.registrorural.com.br/
- TERRAS CARMap: https://www.terras.agr.br/carmap
- GAMAGeo: https://www.gamageo.com/cadastro-ambiental-rural
- NatiGeo: https://natigeo.com/servicos/car-cadastro-ambiental-rural/

## Evidencia de mercado usada

- O CAR oficial e gratuito para o cidadao. Isso enfraquece uma licenca paga direta ao pequeno produtor.
- MAPADOCAR descreve um sistema web gratuito para profissionais elaborarem CAR com desenho, calculo, importacao/exportacao e bases geograficas. E o benchmark mais proximo e reduz a originalidade do escopo atual.
- Registro Rural oferece consultas, mapas, KML/KMZ e relatorios por assinatura, com plano PRO exibido a R$ 149,90 por mes no acesso realizado. Isso e sinal de disposicao B2B para pagar por produtividade e dados, nao prova de demanda para o GeoRascunho.
- GAMAGeo e NatiGeo comercializam servicos de mapeamento, inscricao e retificacao. Isso indica mercado de servico tecnico, sem comprovar um mercado SaaS direto ao produtor.
- A Consulta Publica oficial de maio de 2026 ja oferece mapa interativo, download vetorial filtrado, indicadores e historico de retificacoes.
- O modulo pre-preenchido ja verifica dados fundiarios e geograficos e reduz trabalho cadastral. O GeoRascunho precisa se diferenciar por fluxo de correcao explicavel, evidencias locais e revisao humana.

## Limites da avaliacao

- Nao foram entrevistados produtores, tecnicos, analistas estaduais ou compradores.
- Nao ha dados de numero de equipes, qualidade dos concorrentes ou distribuicao das notas. Nao foi atribuida probabilidade numerica de premiacao.
- Precos e alegacoes de fornecedores foram usados apenas como sinais de mercado e concorrencia; nao foram tratados como fatos regulatorios.
- A pagina oficial de busca web integrada retornou erro 403. As paginas foram acessadas diretamente por suas URLs e o texto foi salvo temporariamente para auditoria.
- A pontuacao do parecer e diagnostica, nao uma nota oficial da Comissao Julgadora.

## Estrutura do relatorio

- Titulo: presente.
- Executive Summary: presente, imediatamente apos o titulo.
- Evidencias e interpretacao: placar, riscos, requisitos e mercado.
- Proximos passos: versao competitiva recomendada.
- Perguntas em aberto: validacoes que podem mudar a decisao.
- Ressalvas: limites e incertezas materiais.
