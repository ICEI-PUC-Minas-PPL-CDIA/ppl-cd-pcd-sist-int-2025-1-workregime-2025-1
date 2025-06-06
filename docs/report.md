# Regime de Trabalho na Área de Dados: Preferências Entre Remoto, Híbrido e Presencial


**Luiz Felipe Assis Cavalcante, lfacavalcante@sga.pucminas.br**

**João Vitor de Lima, joao.lima.1594303@sga.pucminas.br**

**Márcio Douglas Cassemiro Junior, marcio.cassemiro@sga.pucminas.br**

**Gustavo Horta, gustavo.horta.1524459@sga.pucminas.br**


---

Professores:

** Prof. Hugo de Paula **
** Prof. Hayala Curto**

---

_Curso de Ciência de Dados, Unidade Praça da Liberdade_

_Instituto de Informática e Ciências Exatas – Pontifícia Universidade de Minas Gerais (PUC MINAS), Belo Horizonte – MG – Brasil_

---

_**Resumo**. Escrever aqui o resumo. O resumo deve contextualizar rapidamente o trabalho, descrever seu objetivo e, ao final, 
mostrar algum resultado relevante do trabalho (até 10 linhas)._

---

## 📑 Índice

- [Introdução](#introdução)
	- [Contextualização](#contextualização)
	- [Problema](#problema)
	- [Objetivo Geral](#objetivo-geral)
  		- [Objetivos Específicos](#objetivos-específicos)
	- [Justificativas](#justificativas)
- [Público-alvo](#público-alvo)
- [Análise Exploratória dos Dados](#an%C3%A1lise-explorat%C3%B3rida-dos-dados).
  	- [Dicionário de Dados](#dicionário-de-dados)
  		- [State_of_data_BR_2023_Kaggle - df_survey_2023](#state_of_data_br_2023_kaggle---df_survey_2023)
  	   	- [PNAD_Roubos_Furtos_Brasil_2023](#pnad_roubos_furtos_brasil_2023)
  	  	- [PNAD Média Horas Semanais de Trabalho Doméstico por Cor ou Raça - Brasil](#pnad-média-horas-semanais-de-trabalho-doméstico-por-cor-ou-raça---brasil)
	- [Descrição dos Dados](#descrição-de-dados)
  		- [Análise Exploratória dos Dados - State_of_data_BR_2023_Kaggle](#análise-exploratória-dos-dados---state_of_data_br_2023_kaggle---df_survey_2023)
  		- [Análise Exploratória dos Dados - PNAD Roubos e Furtos (Brasil)](#análise-exploratória-dos-dados---pnad-roubos-e-furtos-brasil)
   		- [Análise Exploratória dos Dados - PNAD Média Horas de Trabalho Doméstico por Cor ou Raça (Brasil)](#pnad_tempo_trab_dom%C3%A9stico---df_trabalho_domestico)
- [Preparação dos Dados](#preparação-dos-dados)
	- [Seleção de Atributos](#seleção-de-atributos)
- [Indução de modelos](#indução-de-modelos)
	- [Modelo 1: Decision Tree](#modelo-1-árvore-de-decisão)
 	- [Modelo 2: Random Forest](#modelo-2-random-forest)
- [Resultados](#resultados)
     - [Resultados obtidos com o modelo 1](#resultados-obtidos-com-o-modelo-1)
 		- [Análise da Matriz de Confusão](#análise-da-matriz-de-confusão-do-modelo-1)
   		- [Interpretação do modelo 1](#interpreta%C3%A7%C3%A3o-do-modelo-1)
     - [Resultados obtidos com o modelo 2](#resultados-obtidos-com-o-modelo-2)
 		- [Análise da Matriz de Confusão](#análise-da-matriz-de-confusão-do-modelo-2)
   		- [Interpretação do modelo 2](#interpretação-do-modelo-2)
- [Análise comparativa dos modelos](#análise-comparativa-dos-modelos)
- [Conclusão](#8-conclus%C3%A3o)
- [Referências](#refer%C3%AAncias)
- [Apêndices](#ap%C3%AAndices)
---


##	Introdução

A escolha do regime de trabalho — remoto, híbrido ou presencial — tem se tornado um tema central nas discussões sobre a dinâmica do mercado de trabalho, especialmente após a pandemia de Covid-19. Com a aceleração da adoção do trabalho remoto, muitos profissionais passaram a reconsiderar suas preferências quanto à flexibilidade e à forma como suas atividades são realizadas. No setor de dados, onde a tecnologia e a produtividade estão fortemente interligadas, a adaptação a novos modelos de trabalho gerou tanto benefícios quanto desafios.

Esse cenário levanta a questão sobre quais fatores determinam as escolhas dos profissionais de dados em relação ao regime de trabalho. A análise de aspectos como produtividade, tempo de deslocamento, saúde mental, flexibilidade e o impacto da interação social se torna essencial para entender as dinâmicas desse grupo específico. Compreender essas preferências pode não apenas ajudar a identificar as melhores práticas para aumentar a satisfação e a produtividade dos profissionais, mas também fornecer insights valiosos para empresas que buscam se adaptar às novas realidades do trabalho no pós-pandemia.

Este trabalho, portanto, tem como objetivo explorar os principais fatores que influenciam a escolha dos profissionais da área de dados quanto ao regime de trabalho. Dada a natureza altamente digital e analítica desse setor, compreender como elementos como produtividade, tempo de deslocamento, saúde mental, flexibilidade e interação social impactam suas preferências é essencial. A análise dessas variáveis pode fornecer insights valiosos tanto para profissionais que buscam otimizar seu desempenho e bem-estar quanto para empresas que precisam estruturar políticas de trabalho mais eficientes e alinhadas às demandas desse mercado específico.


###    Contextualização

A pandemia de Covid-19 acelerou mudanças na organização do trabalho, especialmente em áreas como tecnologia e dados, onde a digitalização permitiu uma rápida adaptação ao modelo remoto. Muitos profissionais do setor relataram ganhos em produtividade e qualidade de vida devido à flexibilidade e à eliminação do tempo de deslocamento, embora desafios como o isolamento social e a separação entre vida pessoal e profissional tenham surgido. Com a flexibilização das restrições, empresas adotaram diferentes regimes de trabalho, mas muitos profissionais de dados passaram a preferir o home office ou modelos híbridos.

###    Problema

O presente estudo busca ajudar empresas a compreender as prioridades de seus funcionários em relação ao regime de trabalho, com o objetivo de identificar os fatores que influenciam a escolha entre os modelos remoto, híbrido ou presencial. A pesquisa visa responder à seguinte pergunta orientada por dados: quais aspectos são determinantes para os profissionais na decisão de adotar um desses regimes de trabalho? Através dessa análise, espera-se fornecer insights valiosos para que as empresas possam ajustar suas políticas de trabalho de forma a atender melhor às necessidades e preferências de seus colaboradores.

> **Links Úteis**:
> - [Objetivos, Problema de pesquisa e Justificativa](https://medium.com/@versioparole/objetivos-problema-de-pesquisa-e-justificativa-c98c8233b9c3)


###    Objetivo geral

Desenvolver um sistema inteligente capaz de identificar padrões na escolha do regime de trabalho (remoto, híbrido ou presencial) e analisar os principais fatores que influenciam essa decisão. O sistema levará em consideração aspectos como mobilidade urbana, cargo, preferências dos profissionais e outras variáveis relevantes, gerando insights para empresas e formuladores de políticas trabalhistas.

####    Objetivos específicos

- Identificar os principais fatores que influenciam a escolha dos profissionais de dados pelo regime de trabalho remoto, híbrido ou presencial.  
- Analisar a variação das preferências por regime de trabalho de acordo com cargo, setor de atuação e localização.  
- Comparar os impactos da interação social e do tempo de deslocamento na decisão pelo modelo de trabalho adotado.  

> **Links Úteis**:
> - [Objetivo geral e objetivo específico: como fazer e quais verbos utilizar](https://blog.mettzer.com/diferenca-entre-objetivo-geral-e-objetivo-especifico/)

###    Justificativas

Este estudo se justifica pela necessidade de fornecer uma base analítica que auxilie empresas na formulação de cargos e na escolha do regime de trabalho mais adequado, considerando o perfil dos profissionais que possuem ou desejam atrair. Ao identificar os fatores que influenciam essa decisão, a pesquisa permite que organizações alinhem suas estratégias às expectativas do mercado, reduzindo a rotatividade e aumentando o engajamento dos colaboradores.

Além disso, compreender a relação entre fatores como cargo, setor de atuação, tempo de deslocamento e interação social pode ajudar empresas a ajustar suas políticas de trabalho para atender melhor às necessidades dos profissionais. Dessa forma, a pesquisa contribui para a construção de ambientes mais flexíveis e alinhados às novas dinâmicas do mercado pós-pandemia, beneficiando tanto as empresas quanto os trabalhadores.

> **Links Úteis**:
> - [Como montar a justificativa](https://guiadamonografia.com.br/como-montar-justificativa-do-tcc/)

##    Público alvo

O público-alvo desse sistema inclui empresas de diversos setores que desejam entender melhor as preferências de seus funcionários em relação ao regime de trabalho, auxiliando na formulação de políticas mais eficientes e atrativas. Além disso, gestores de Recursos Humanos podem utilizá-lo para otimizar modelos de trabalho e retenção de talentos. Pesquisadores e formuladores de políticas públicas também podem se beneficiar dos dados gerados para analisar impactos na mobilidade urbana, produtividade e qualidade de vida dos trabalhadores. Startups e consultorias especializadas em transformação digital e cultura organizacional podem usar os insights do sistema para oferecer soluções personalizadas a seus clientes.

> **Links Úteis**:
> - [Público-alvo](https://blog.hotmart.com/pt-br/publico-alvo/)
> - [Como definir o público alvo](https://exame.com/pme/5-dicas-essenciais-para-definir-o-publico-alvo-do-seu-negocio/)
> - [Público-alvo: o que é, tipos, como definir seu público e exemplos](https://klickpages.com.br/blog/publico-alvo-o-que-e/)
> - [Qual a diferença entre público-alvo e persona?](https://rockcontent.com/blog/diferenca-publico-alvo-e-persona/)

## Análise exploratórida dos dados

###    Dicionário de dados
 
#### `State_of_data_BR_2023_Kaggle - df_survey_2023`
Essa base de dados contém os dados relacionados aos profissionais de dados que serão utilizados como base para o atual estudo

Os atributos que compõem o dataset são:

<details>
	<summary>📌Clique para ver todos os atributos⬇️</summary>
	
| Atributo | Tipo |
|----------|------|
| ('P0', 'id') | Quantitativo Discreto |
| ('P1_a ', 'Idade') | Quantitativo Contínuo |
| ('P1_a_1 ', 'Faixa idade') | Categórico Polinomial Não Ordinal |
| ('P1_b ', 'Genero') | Categórico Polinomial Não Ordinal |
| ('P1_c ', 'Cor/raca/etnia') | Categórico Polinomial Não Ordinal |
| ('P1_d ', 'PCD') | Categórico Binário |
| ('P1_e ', 'experiencia_profissional_prejudicada') | Categórico Polinomial Não Ordinal |
| ('P1_e_1 ', 'Não acredito que minha experiência profissional seja afetada') | Categórico Binário |
| ('P1_e_2 ', 'Experiencia prejudicada devido a minha Cor Raça Etnia') | Categórico Binário |
| ('P1_e_3 ', 'Experiencia prejudicada devido a minha identidade de gênero') | Categórico Binário |
| ('P1_e_4 ', 'Experiencia prejudicada devido ao fato de ser PCD') | Categórico Binário |
| ('P1_f ', 'aspectos_prejudicados') | Categórico Polinomial Não Ordinal |
| ('P1_f_1', 'Quantidade de oportunidades de emprego/vagas recebidas') | Categórico Binário |
| ('P1_f_2', 'Senioridade das vagas recebidas em relação à sua experiência') | Categórico Binário |
| ('P1_f_3', 'Aprovação em processos seletivos/entrevistas') | Categórico Binário |
| ('P1_f_4', 'Oportunidades de progressão de carreira') | Categórico Binário |
| ('P1_f_5', 'Velocidade de progressão de carreira') | Categórico Binário |
| ('P1_f_6', 'Nível de cobrança no trabalho/Stress no trabalho') | Categórico Binário |
| ('P1_f_7', 'Atenção dada diante das minhas opiniões e ideias') | Categórico Binário |
| ('P1_f_8', 'Relação com outros membros da empresa, em momentos de trabalho') | Categórico Binário |
| ('P1_f_9', 'Relação com outros membros da empresa, em momentos de integração e outros momentos fora do trabalho') | Categórico Binário |
| ('P1_g ', 'vive_no_brasil') | Categórico Binário |
| ('P1_i ', 'Estado onde mora') | Categórico Polinomial Não Ordinal |
| ('P1_i_1 ', 'uf onde mora') | Categórico Polinomial Não Ordinal |
| ('P1_i_2 ', 'Regiao onde mora') | Categórico Polinomial Não Ordinal |
| ('P1_j ', 'Mudou de Estado?') | Categórico Binário |
| ('P1_k ', 'Regiao de origem') | Categórico Polinomial Não Ordinal |
| ('P1_l ', 'Nivel de Ensino') | Categórico Polinomial Não Ordinal |
| ('P1_m ', 'Área de Formação') | Categórico Polinomial Não Ordinal |
| ('P2_a ', 'Qual sua situação atual de trabalho?') | Categórico Polinomial Não Ordinal |
| ('P2_b ', 'Setor') | Categórico Polinomial Não Ordinal |
| ('P2_c ', 'Numero de Funcionarios') | Categórico Polinomial Não Ordinal |
| ('P2_d ', 'Gestor?') | Categórico Binário |
| ('P2_e ', 'Cargo como Gestor') | Categórico Polinomial Não Ordinal |
| ('P2_f ', 'Cargo Atual') | Categórico Polinomial Não Ordinal |
| ('P2_g ', 'Nivel') | Categórico Polinomial Ordinal |
| ('P2_h ', 'Faixa salarial') | Categórico Polinomial Ordinal |
| ('P2_i ', 'Quanto tempo de experiência na área de dados você tem?') | Categórico Polinomial Ordinal |
| ('P2_j ', 'Quanto tempo de experiência na área de TI/Engenharia de Software você teve antes de começar a trabalhar na área de dados?') | Categórico Polinomial Ordinal |
| ('P2_k ', 'Você está satisfeito na sua empresa atual?') | Categórico Binário |
| ('P2_l ', 'Qual o principal motivo da sua insatisfação com a empresa atual?') | Categórico Polinomial Não Ordinal |
| ('P2_l_1 ', 'Falta de oportunidade de crescimento no emprego atual') | Categórico Binário |
| ('P2_l_2 ', 'Salário atual não corresponde ao mercado') | Categórico Binário |
| ('P2_l_3 ', 'Não tenho uma boa relação com meu líder/gestor') | Categórico Binário |
| ('P2_l_4 ', 'Gostaria de trabalhar em em outra área de atuação') | Categórico Binário |
| ('P2_l_5 ', 'Gostaria de receber mais benefícios') | Categórico Binário |
| ('P2_l_6 ', 'O clima de trabalho/ambiente não é bom') | Categórico Binário |
| ('P2_l_7 ', 'Falta de maturidade analítica na empresa') | Categórico Binário |
| ('P2_m ', 'Você participou de entrevistas de emprego nos últimos 6 meses?') | Categórico Polinomial Não Ordinal |
| ('P2_n ', 'Você pretende mudar de emprego nos próximos 6 meses?') | Categórico Polinomial Não Ordinal |
| ('P2_o ', 'Quais os principais critérios que você leva em consideração no momento de decidir onde trabalhar?') | Categórico Polinomial Não Ordinal |
| ('P2_o_1 ', 'Remuneração/Salário') | Categórico Binário |
| ('P2_o_2 ', 'Benefícios') | Categórico Binário |
| ('P2_o_3 ', 'Propósito do trabalho e da empresa') | Categórico Binário |
| ('P2_o_4 ', 'Flexibilidade de trabalho remoto') | Categórico Binário |
| ('P2_o_5 ', 'Ambiente e clima de trabalho') | Categórico Binário |
| ('P2_o_6 ', 'Oportunidade de aprendizado e trabalhar com referências na área') | Categórico Binário |
| ('P2_o_7 ', 'Plano de carreira e oportunidades de crescimento profissional') | Categórico Binário |
| ('P2_o_8 ', 'Maturidade da empresa em termos de tecnologia e dados') | Categórico Binário |
| ('P2_o_9 ', 'Qualidade dos gestores e líderes') | Categórico Binário |
| ('P2_o_10 ', 'Reputação que a empresa tem no mercado') | Categórico Binário |
| ('P2_q ', 'Empresa que trabaha passou por layoff em 2023') | Categórico Polinomial Não Ordinal |
| ('P2_r ', 'Atualmente qual a sua forma de trabalho?') | Categórico Polinomial Não Ordinal |
| ('P2_s ', 'Qual a forma de trabalho ideal para você?') | Categórico Polinomial Não Ordinal |
| ('P2_t ', 'Caso sua empresa decida pelo modelo 100% presencial qual será sua atitude?') | Categórico Polinomial Não Ordinal |
| ('P3_a ', 'Qual o número aproximado de pessoas que atuam com dados na sua empresa hoje?') | Categórico Polinomial Não Ordinal |
| ('P3_b ', 'Quais desses papéis/cargos fazem parte do time (ou chapter) de dados da sua empresa?') | Categórico Polinomial Não Ordinal |
| ('P3_b_1 ', 'Analytics Engineer') | Categórico Binário |
| ('P3_b_2 ', 'Engenharia de Dados/Data Engineer') | Categórico Binário |
| ('P3_b_3 ', 'Analista de Dados/Data Analyst') | Categórico Binário |
| ('P3_b_4 ', 'Cientista de Dados/Data Scientist') | Categórico Binário |
| ('P3_b_5 ', 'Database Administrator/DBA') | Categórico Binário |
| ('P3_b_6 ', 'Analista de Business Intelligence/BI') | Categórico Binário |
| ('P3_b_7 ', 'Arquiteto de Dados/Data Architect') | Categórico Binário |
| ('P3_b_8 ', 'Data Product Manager/DPM') | Categórico Binário |
| ('P3_b_9 ', 'Business Analyst') | Categórico Binário |
| ('P3_c ', 'Quais dessas responsabilidades fazem parte da sua rotina atual de trabalho como gestor?') | Categórico Polinomial Não Ordinal |
| ('P3_c_1 ', 'Pensar na visão de longo prazo de dados da empresa e fortalecimento da cultura analítica da companhia.') | Categórico Binário |
| ('P3_c_2 ', 'Organização de treinamentos e iniciativas com o objetivo de aumentar a maturidade analítica das áreas de negócios.') | Categórico Binário |
| ('P3_c_3 ', 'Atração, seleção e contratação de talentos para o time de dados.') | Categórico Binário |
| ('P3_c_4 ', 'Decisão sobre contratação de ferramentas e tecnologias relacionadas a dados.') | Categórico Binário |
| ('P3_c_5 ', 'Sou gestor da equipe responsável pela engenharia de dados e por manter o Data Lake da empresa como fonte única dos dados, garantindo a qualidade e confiabilidade da informação.') | Categórico Binário |
| ('P3_c_6 ', 'Sou gestor da equipe responsável pela entrega de dados, estudos, relatórios e dashboards para as áreas de negócio da empresa.') | Categórico Binário |
| ('P3_c_7 ', 'Sou gestor da equipe responsável por iniciativas e projetos envolvendo Inteligência Artificial e Machine Learning.') | Categórico Binário |
| ('P3_c_8 ', 'Apesar de ser gestor ainda atuo na parte técnica, construindo soluções/análises/modelos etc.') | Categórico Binário |
| ('P3_c_9 ', 'Gestão de projetos de dados, cuidando das etapas, equipes envolvidas, atingimento dos objetivos etc.') | Categórico Binário |
| ('P3_c_10 ', 'Gestão de produtos de dados, cuidando da visão dos produtos, backlog, feedback de usuários etc.') | Categórico Binário |
| ('P3_c_11 ', 'Gestão de pessoas, apoio no desenvolvimento das pessoas, evolução de carreira') | Categórico Binário |
| ('P3_d ', 'Quais são os 3 maiores desafios que você tem como gestor no atual momento?') | Categórico Polinomial Não Ordinal |
| ('P3_d_1 ', 'a Contratar novos talentos.') | Categórico Binário |
| ('P3_d_2 ', 'b Reter talentos.') | Categórico Binário |
| ('P3_d_3 ', 'c Convencer a empresa a aumentar os investimentos na área de dados.') | Categórico Binário |
| ('P3_d_4 ', 'd Gestão de equipes no ambiente remoto.') | Categórico Binário |
| ('P3_d_5 ', 'e Gestão de projetos envolvendo áreas multidisciplinares da empresa.') | Categórico Binário |
| ('P3_d_6 ', 'f Organizar as informações e garantir a qualidade e confiabilidade.') | Categórico Binário |
| ('P3_d_7 ', 'g Conseguir processar e armazenar um alto volume de dados.') | Categórico Binário |
| ('P3_d_8 ', 'h Conseguir gerar valor para as áreas de negócios através de estudos e experimentos.') | Categórico Binário |
| ('P3_d_9 ', 'i Desenvolver e manter modelos Machine Learning em produção.') | Categórico Binário |
| ('P3_d_10 ', 'j Gerenciar a expectativa das áreas de negócio em relação as entregas das equipes de dados.') | Categórico Binário |
| ('P3_d_11 ', 'k Garantir a manutenção dos projetos e modelos em produção, em meio ao crescimento da empresa.') | Categórico Binário |
| ('P3_d_12 ', 'Conseguir levar inovação para a empresa através dos dados.') | Categórico Binário |
| ('P3_d_13 ', 'Garantir retorno do investimento (ROI) em projetos de dados.') | Categórico Binário |
| ('P3_d_14 ', 'Dividir o tempo entre entregas técnicas e gestão.') | Categórico Binário |
| ('P3_e ', 'AI Generativa é uma prioridade em sua empresa?') | Categórico Polinomial Não Ordinal |
| ('P3_f ', 'Tipos de uso de AI Generativa e LLMs na empresa') | Categórico Polinomial Não Ordinal |
| ('P3_f_1 ', 'Colaboradores usando AI generativa de forma independente e descentralizada') | Categórico Binário |
| ('P3_f_2 ', 'Direcionamento centralizado do uso de AI generativa') | Categórico Binário |
| ('P3_f_3 ', 'Desenvolvedores utilizando Copilots') | Categórico Binário |
| ('P3_f_4 ', 'AI Generativa e LLMs para melhorar produtos externos') | Categórico Binário |
| ('P3_f_5 ', 'AI Generativa e LLMs para melhorar produtos internos para os colaboradores') | Categórico Binário |
| ('P3_f_6 ', 'IA Generativa e LLMs como principal frente do negócio') | Categórico Binário |
| ('P3_f_7 ', 'IA Generativa e LLMs não é prioridade') | Categórico Binário |
| ('P3_f_8 ', 'Não sei opinar sobre o uso de IA Generativa e LLMs na empresa') | Categórico Binário |
| ('P3_g ', 'Motivos que levam a empresa a não usar AI Genrativa e LLMs') | Categórico Polinomial Não Ordinal |
| ('P3_g_1 ', 'Falta de compreensão dos casos de uso') | Categórico Binário |
| ('P3_g_2 ', 'Falta de confiabilidade das saídas (alucinação dos modelos)') | Categórico Binário |
| ('P3_g_3 ', 'Incerteza em relação a regulamentação') | Categórico Binário |
| ('P3_g_4 ', 'Preocupações com segurança e privacidade de dados') | Categórico Binário |
| ('P3_g_5 ', 'Retorno sobre investimento (ROI) não comprovado de IA Generativa') | Categórico Binário |
| ('P3_g_6 ', 'Dados da empresa não estão prontos para uso de IA Generativa') | Categórico Binário |
| ('P3_g_7 ', 'Falta de expertise ou falta de recursos') | Categórico Binário |
| ('P3_g_8 ', 'Alta direção da empresa não vê valor ou não vê como prioridade') | Categórico Binário |
| ('P3_g_9 ', 'Preocupações com propriedade intelectual') | Categórico Binário |
| ('P4_a ', 'Mesmo que esse não seja seu cargo formal, você considera que sua atuação no dia a dia, reflete alguma das opções listadas abaixo?') | Categórico Polinomial Não Ordinal |
| ('P4_a_1 ', 'Atuacao') | Categórico Polinomial Não Ordinal |
| ('P4_b ', 'Quais das fontes de dados listadas você já analisou ou processou no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P4_b_1 ', 'Dados relacionais (estruturados em bancos SQL)') | Categórico Binário |
| ('P4_b_2 ', 'Dados armazenados em bancos NoSQL') | Categórico Binário |
| ('P4_b_3 ', 'Imagens') | Categórico Binário |
| ('P4_b_4 ', 'Textos/Documentos') | Categórico Binário |
| ('P4_b_5 ', 'Vídeos') | Categórico Binário |
| ('P4_b_6 ', 'Áudios') | Categórico Binário |
| ('P4_b_7 ', 'Planilhas') | Categórico Binário |
| ('P4_b_8 ', 'Dados georeferenciados') | Categórico Binário |
| ('P4_c ', 'Entre as fontes de dados listadas, quais você utiliza na maior parte do tempo?') | Categórico Polinomial Não Ordinal |
| ('P4_c_1 ', 'Dados relacionais (estruturados em bancos SQL)') | Categórico Binário |
| ('P4_c_2 ', 'Dados armazenados em bancos NoSQL') | Categórico Binário |
| ('P4_c_3 ', 'Imagens') | Categórico Binário |
| ('P4_c_4 ', 'Textos/Documentos') | Categórico Binário |
| ('P4_c_5 ', 'Vídeos') | Categórico Binário |
| ('P4_c_6 ', 'Áudios') | Categórico Binário |
| ('P4_c_7 ', 'Planilhas') | Categórico Binário |
| ('P4_c_8 ', 'Dados georeferenciados') | Categórico Binário |
| ('P4_d ', 'Quais das linguagens listadas abaixo você utiliza no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P4_d_1 ', 'SQL') | Categórico Binário |
| ('P4_d_2 ', 'R ') | Categórico Binário |
| ('P4_d_3 ', 'Python') | Categórico Binário |
| ('P4_d_4 ', 'C/C++/C#') | Categórico Binário |
| ('P4_d_5 ', '.NET') | Categórico Binário |
| ('P4_d_6 ', 'Java') | Categórico Binário |
| ('P4_d_7 ', 'Julia') | Categórico Binário |
| ('P4_d_8 ', 'SAS/Stata') | Categórico Binário |
| ('P4_d_9 ', 'Visual Basic/VBA') | Categórico Binário |
| ('P4_d_10 ', 'Scala') | Categórico Binário |
| ('P4_d_11 ', 'Matlab') | Categórico Binário |
| ('P4_d_12 ', 'Rust') | Categórico Binário |
| ('P4_d_13 ', 'PHP') | Categórico Binário |
| ('P4_d_14 ', 'JavaScript') | Categórico Binário |
| ('P4_d_15 ', 'Não utilizo nenhuma linguagem') | Categórico Binário |
| ('P4_e ', 'Entre as linguagens listadas abaixo, qual é a que você mais utiliza no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P4_f ', 'Entre as linguagens listadas abaixo, qual é a sua preferida?') | Categórico Polinomial Não Ordinal |
| ('P4_g ', 'Quais dos bancos de dados/fontes de dados listados abaixo você utiliza no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P4_g_1 ', 'MySQL') | Categórico Binário |
| ('P4_g_2 ', 'Oracle') | Categórico Binário |
| ('P4_g_3 ', 'SQL SERVER') | Categórico Binário |
| ('P4_g_4 ', 'Amazon Aurora ou RDS') | Categórico Binário |
| ('P4_g_5 ', 'DynamoDB') | Categórico Binário |
| ('P4_g_6 ', 'CoachDB') | Categórico Binário |
| ('P4_g_7 ', 'Cassandra') | Categórico Binário |
| ('P4_g_8 ', 'MongoDB') | Categórico Binário |
| ('P4_g_9 ', 'MariaDB') | Categórico Binário |
| ('P4_g_10 ', 'Datomic') | Categórico Binário |
| ('P4_g_11 ', 'S3') | Categórico Binário |
| ('P4_g_12 ', 'PostgreSQL') | Categórico Binário |
| ('P4_g_13 ', 'ElasticSearch') | Categórico Binário |
| ('P4_g_14 ', 'DB2') | Categórico Binário |
| ('P4_g_15 ', 'Microsoft Access') | Categórico Binário |
| ('P4_g_16 ', 'SQLite') | Categórico Binário |
| ('P4_g_17 ', 'Sybase') | Categórico Binário |
| ('P4_g_18 ', 'Firebase') | Categórico Binário |
| ('P4_g_19 ', 'Vertica') | Categórico Binário |
| ('P4_g_20 ', 'Redis') | Categórico Binário |
| ('P4_g_21 ', 'Neo4J') | Categórico Binário |
| ('P4_g_22 ', 'Google BigQuery') | Categórico Binário |
| ('P4_g_23 ', 'Google Firestore') | Categórico Binário |
| ('P4_g_24 ', 'Amazon Redshift') | Categórico Binário |
| ('P4_g_25 ', 'Amazon Athena') | Categórico Binário |
| ('P4_g_26 ', 'Snowflake') | Categórico Binário |
| ('P4_g_27 ', 'Databricks') | Categórico Binário |
| ('P4_g_28 ', 'HBase') | Categórico Binário |
| ('P4_g_29 ', 'Presto') | Categórico Binário |
| ('P4_g_30 ', 'Splunk') | Categórico Binário |
| ('P4_g_31 ', 'SAP HANA') | Categórico Binário |
| ('P4_g_32 ', 'Hive') | Categórico Binário |
| ('P4_g_33 ', 'Firebird') | Categórico Binário |
| ('P4_h ', 'Dentre as opções listadas, qual sua Cloud preferida?') | Categórico Polinomial Não Ordinal |
| ('P4_h_1 ', 'Azure (Microsoft)') | Categórico Binário |
| ('P4_h_2 ', 'Amazon Web Services (AWS)') | Categórico Binário |
| ('P4_h_3 ', 'Google Cloud (GCP)') | Categórico Binário |
| ('P4_h_4 ', 'Oracle Cloud') | Categórico Binário |
| ('P4_h_5 ', 'IBM') | Categórico Binário |
| ('P4_h_6 ', 'Servidores On Premise/Não utilizamos Cloud') | Categórico Binário |
| ('P4_h_7 ', 'Cloud Própria') | Categórico Binário |
| ('P4_i ', 'Cloud preferida') | Categórico Polinomial Não Ordinal |
| ('P4_j ', 'Ferramenta de BI utilizada no dia a dia') | Categórico Polinomial Não Ordinal |
| ('P4_j_1 ', 'Microsoft PowerBI') | Categórico Binário |
| ('P4_j_2 ', 'Qlik View/Qlik Sense') | Categórico Binário |
| ('P4_j_3 ', 'Tableau') | Categórico Binário |
| ('P4_j_4 ', 'Metabase') | Categórico Binário |
| ('P4_j_5 ', 'Superset') | Categórico Binário |
| ('P4_j_6 ', 'Redash') | Categórico Binário |
| ('P4_j_7 ', 'Looker') | Categórico Binário |
| ('P4_j_8 ', 'Looker Studio(Google Data Studio)') | Categórico Binário |
| ('P4_j_9 ', 'Amazon Quicksight') | Categórico Binário |
| ('P4_j_10 ', 'Mode') | Categórico Binário |
| ('P4_j_11 ', 'Alteryx') | Categórico Binário |
| ('P4_j_12 ', 'MicroStrategy') | Categórico Binário |
| ('P4_j_13 ', 'IBM Analytics/Cognos') | Categórico Binário |
| ('P4_j_14 ', 'SAP Business Objects/SAP Analytics') | Categórico Binário |
| ('P4_j_15 ', 'Oracle Business Intelligence') | Categórico Binário |
| ('P4_j_16 ', 'Salesforce/Einstein Analytics') | Categórico Binário |
| ('P4_j_17 ', 'Birst') | Categórico Binário |
| ('P4_j_18 ', 'SAS Visual Analytics') | Categórico Binário |
| ('P4_j_19 ', 'Grafana') | Categórico Binário |
| ('P4_j_20 ', 'TIBCO Spotfire') | Categórico Binário |
| ('P4_j_21 ', 'Pentaho') | Categórico Binário |
| ('P4_j_22 ', 'Fazemos todas as análises utilizando apenas Excel ou planilhas do google') | Categórico Binário |
| ('P4_j_23 ', 'Não utilizo nenhuma ferramenta de BI no trabalho') | Categórico Binário |
| ('P4_k ', 'Qual sua ferramenta de BI preferida?') | Categórico Polinomial Não Ordinal |
| ('P4_l ', 'Qual o tipo de uso de AI Generativa e LLMs na empresa') | Categórico Polinomial Não Ordinal |
| ('P4_l_1 ', 'Colaboradores usando AI generativa de forma independente e descentralizada') | Categórico Binário |
| ('P4_l_2 ', 'Direcionamento centralizado do uso de AI generativa') | Categórico Binário |
| ('P4_l_3 ', 'Desenvolvedores utilizando Copilots') | Categórico Binário |
| ('P4_l_4 ', 'AI Generativa e LLMs para melhorar produtos externos para os clientes finais') | Categórico Binário |
| ('P4_l_5 ', 'AI Generativa e LLMs para melhorar produtos internos para os colaboradores') | Categórico Binário |
| ('P4_l_6 ', 'IA Generativa e LLMs como principal frente do negócio') | Categórico Binário |
| ('P4_l_7 ', 'IA Generativa e LLMs não é prioridade') | Categórico Binário |
| ('P4_l_8 ', 'Não sei opinar sobre o uso de IA Generativa e LLMs na empresa') | Categórico Binário |
| ('P4_m ', 'Utiliza ChatGPT ou LLMs no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P4_m_1 ', 'Não uso soluções de AI Generativa com foco em produtividade') | Categórico Binário |
| ('P4_m_2 ', 'Uso soluções gratuitas de AI Generativa com foco em produtividade') | Categórico Binário |
| ('P4_m_3 ', 'Uso e pago pelas soluções de AI Generativa com foco em produtividade') | Categórico Binário |
| ('P4_m_4 ', 'A empresa que trabalho paga pelas soluções de AI Generativa com foco em produtividade') | Categórico Binário |
| ('P4_m_5 ', 'Uso soluções do tipo Copilot') | Categórico Binário |
| ('P5_a ', 'Qual seu objetivo na área de dados?') | Categórico Polinomial Não Ordinal |
| ('P5_b ', 'Qual oportunidade você está buscando?') | Categórico Polinomial Não Ordinal |
| ('P5_c ', 'Há quanto tempo você busca uma oportunidade na área de dados?') | Categórico Polinomial Não Ordinal |
| ('P5_d ', 'Como tem sido a busca por um emprego na área de dados?') | Categórico Polinomial Não Ordinal |
| ('P6_a ', 'Quais das opções abaixo fazem parte da sua rotina no trabalho atual como engenheiro de dados?') | Categórico Polinomial Não Ordinal |
| ('P6_a_1 ', 'Desenvolvo pipelines de dados utilizando linguagens de programação como Python, Scala, Java etc.') | Categórico Binário |
| ('P6_a_2 ', 'Realizo construções de ETL's em ferramentas como Pentaho, Talend, Dataflow etc.') | Categórico Binário |
| ('P6_a_3 ', 'Crio consultas através da linguagem SQL para exportar informações e compartilhar com as áreas de negócio.') | Categórico Binário |
| ('P6_a_4 ', 'Atuo na integração de diferentes fontes de dados através de plataformas proprietárias como Stitch Data, Fivetran etc.') | Categórico Binário |
| ('P6_a_5 ', 'Modelo soluções de arquitetura de dados, criando componentes de ingestão de dados, transformação e recuperação da informação.') | Categórico Binário |
| ('P6_a_6 ', 'Desenvolvo/cuido da manutenção de repositórios de dados baseados em streaming de eventos como Data Lakes e Data Lakehouses.') | Categórico Binário |
| ('P6_a_7 ', 'Atuo na modelagem dos dados, com o objetivo de criar conjuntos de dados como Data Warehouses, Data Marts etc.') | Categórico Binário |
| ('P6_a_8 ', 'Cuido da qualidade dos dados, metadados e dicionário de dados.') | Categórico Binário |
| ('P6_a_9 ', 'Nenhuma das opções listadas refletem meu dia a dia.') | Categórico Binário |
| ('P6_b ', 'Quais as ferramentas/tecnologias de ETL que você utiliza no trabalho como Data Engineer?') | Categórico Polinomial Não Ordinal |
| ('P6_b_1 ', 'Scripts Python') | Categórico Binário |
| ('P6_b_2 ', 'SQL & Stored Procedures') | Categórico Binário |
| ('P6_b_3 ', 'Apache Airflow') | Categórico Binário |
| ('P6_b_4 ', 'Apache NiFi') | Categórico Binário |
| ('P6_b_5 ', 'Luigi') | Categórico Binário |
| ('P6_b_6 ', 'AWS Glue') | Categórico Binário |
| ('P6_b_7 ', 'Talend') | Categórico Binário |
| ('P6_b_8 ', 'Pentaho') | Categórico Binário |
| ('P6_b_9 ', 'Alteryx') | Categórico Binário |
| ('P6_b_10 ', 'Stitch') | Categórico Binário |
| ('P6_b_11 ', 'Fivetran') | Categórico Binário |
| ('P6_b_12 ', 'Google Dataflow') | Categórico Binário |
| ('P6_b_13 ', 'Oracle Data Integrator') | Categórico Binário |
| ('P6_b_14 ', 'IBM DataStage') | Categórico Binário |
| ('P6_b_15 ', 'SAP BW ETL') | Categórico Binário |
| ('P6_b_16 ', 'SQL Server Integration Services (SSIS)) | Categórico Binário |
| ('P6_b_17 ', 'SAS Data Integration') | Categórico Binário |
| ('P6_b_18 ', 'Qlik Sense') | Categórico Binário |
| ('P6_b_19 ', 'Knime') | Categórico Binário |
| ('P6_b_20 ', 'Databricks') | Categórico Binário |
| ('P6_b_21 ', 'Não utilizo ferramentas de ETL') | Categórico Binário |
| ('P6_c ', 'Sua organização possui um Data Lake?') | Categórico Binário |
| ('P6_d ', 'Qual tecnologia utilizada como plataforma do Data Lake?') | Categórico Polinomial Não Ordinal |
| ('P6_e ', 'Sua organização possui um Data Warehouse?') | Categórico Binário |
| ('P6_f ', 'Qual tecnologia utilizada como plataforma do Data Warehouse?') | Categórico Polinomial Não Ordinal |
| ('P6_g ', 'Quais as ferramentas de gestão de Qualidade de dados, Metadados e catálogo de dados você utiliza no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P6_h ', 'Em qual das opções abaixo você gasta a maior parte do seu tempo?') | Categórico Polinomial Não Ordinal |
| ('P6_h_1 ', 'Desenvolvendo pipelines de dados utilizando linguagens de programação como Python, Scala, Java etc.') | Categórico Binário |
| ('P6_h_2 ', 'Realizando construções de ETL's em ferramentas como Pentaho, Talend, Dataflow etc.') | Categórico Binário |
| ('P6_h_3 ', 'Criando consultas através da linguagem SQL para exportar informações e compartilhar com as áreas de negócio.') | Categórico Binário |
| ('P6_h_4 ', 'Atuando na integração de diferentes fontes de dados através de plataformas proprietárias como Stitch Data, Fivetran etc.') | Categórico Binário |
| ('P6_h_5 ', 'Modelando soluções de arquitetura de dados, criando componentes de ingestão de dados, transformação e recuperação da informação.') | Categórico Binário |
| ('P6_h_6 ', 'Desenvolvendo/cuidando da manutenção de repositórios de dados baseados em streaming de eventos como Data Lakes e Data Lakehouses.') | Categórico Binário |
| ('P6_h_7 ', 'Atuando na modelagem dos dados, com o objetivo de criar conjuntos de dados como Data Warehouses, Data Marts etc.') | Categórico Binário |
| ('P6_h_8 ', 'Cuidando da qualidade dos dados, metadados e dicionário de dados.') | Categórico Binário |
| ('P6_h_9 ', 'Nenhuma das opções listadas refletem meu dia a dia.') | Categórico Binário |
| ('P7_1 ', 'Quais das opções abaixo fazem parte da sua rotina no trabalho atual com análise de dados?') | Categórico Polinomial Não Ordinal |
| ('P7_a_1 ', 'Processo e analiso dados utilizando linguagens de programação como Python, R etc.') | Categórico Binário |
| ('P7_a_2 ', 'Realizo construções de dashboards em ferramentas de BI como PowerBI, Tableau, Looker, Qlik etc.') | Categórico Binário |
| ('P7_a_3 ', 'Crio consultas através da linguagem SQL para exportar informações e compartilhar com as áreas de negócio.') | Categórico Binário |
| ('P7_a_4 ', 'Utilizo API's para extrair dados e complementar minhas análises.') | Categórico Binário |
| ('P7_a_5 ', 'Realizo experimentos e estudos utilizando metodologias estatísticas como teste de hipótese, modelos de regressão etc.') | Categórico Binário |
| ('P7_a_6 ', 'Desenvolvo/cuido da manutenção de ETL's utilizando tecnologias como Talend, Pentaho, Airflow, Dataflow etc.') | Categórico Binário |
| ('P7_a_7 ', 'Atuo na modelagem dos dados, com o objetivo de criar conjuntos de dados, Data Warehouses, Data Marts etc.') | Categórico Binário |
| ('P7_a_8 ', 'Desenvolvo/cuido da manutenção de planilhas para atender as áreas de negócio.') | Categórico Binário |
| ('P7_a_9 ', 'Utilizo ferramentas avançadas de estatística como SASS, PSS, Stata etc') | Categórico Binário |
| ('P7_a_10 ', 'Nenhuma das opções listadas refletem meu dia a dia.') | Categórico Binário |
| ('P7_b ', 'Quais as ferramentas/tecnologias de ETL que você utiliza no trabalho como Data Analyst?') | Categórico Polinomial Não Ordinal |
| ('P7_b_1 ', 'Scripts Python') | Categórico Binário |
| ('P7_b_2 ', 'SQL & Stored Procedures') | Categórico Binário |
| ('P7_b_3 ', 'Apache Airflow') | Categórico Binário |
| ('P7_b_4 ', 'Apache NiFi') | Categórico Binário |
| ('P7_b_5 ', 'Luigi') | Categórico Binário |
| ('P7_b_6 ', 'AWS Glue') | Categórico Binário |
| ('P7_b_7 ', 'Talend') | Categórico Binário |
| ('P7_b_8 ', 'Pentaho') | Categórico Binário |
| ('P7_b_9 ', 'Alteryx') | Categórico Binário |
| ('P7_b_10 ', 'Stitch') | Categórico Binário |
| ('P7_b_11 ', 'Fivetran') | Categórico Binário |
| ('P7_b_12 ', 'Google Dataflow') | Categórico Binário |
| ('P7_b_13 ', 'Oracle Data Integrator') | Categórico Binário |
| ('P7_b_14 ', 'IBM DataStage') | Categórico Binário |
| ('P7_b_15 ', 'SAP BW ETL') | Categórico Binário |
| ('P7_b_16 ', 'SQL Server Integration Services (SSIS)') | Categórico Binário |
| ('P7_b_17 ', 'SAS Data Integration') | Categórico Binário |
| ('P7_b_18 ', 'Qlik Sense') | Categórico Binário |
| ('P7_b_19 ', 'Knime') | Categórico Binário |
| ('P7_b_20 ', 'Databricks') | Categórico Binário |
| ('P7_b_21 ', 'Não utilizo ferramentas de ETL') | Categórico Binário |
| ('P7_c ', 'Sua empresa utiliza alguma das ferramentas listadas para dar mais autonomia em análise de dados para as áreas de negócio?') | Categórico Polinomial Não Ordinal |
| ('P7_c_1 ', 'Ferramentas de AutoML como H2O.ai, Data Robot, BigML etc.') | Categórico Binário |
| ('P7_c_2 ', '""Point and Click"" Analytics como Alteryx, Knime, Rapidminer etc.') | Categórico Binário |
| ('P7_c_3 ', 'Product metricts & Insights como Mixpanel, Amplitude, Adobe Analytics.') | Categórico Binário |
| ('P7_c_4 ', 'Ferramentas de análise dentro de ferramentas de CRM como Salesforce Einstein Anaytics ou Zendesk dashboards.') | Categórico Binário |
| ('P7_c_5 ', 'Minha empresa não utiliza essas ferramentas.') | Categórico Binário |
| ('P7_c_6 ', 'Não sei informar.') | Categórico Binário |
| ('P7_d ', 'Em qual das opções abaixo você gasta a maior parte do seu tempo de trabalho?') | Categórico Polinomial Não Ordinal |
| ('P7_d_1 ', 'Processando e analisando dados utilizando linguagens de programação como Python, R etc.') | Categórico Binário |
| ('P7_d_2 ', 'Realizando construções de dashboards em ferramentas de BI como PowerBI, Tableau, Looker, Qlik etc.') | Categórico Binário |
| ('P7_d_3 ', 'Criando consultas através da linguagem SQL para exportar informações e compartilhar com as áreas de negócio.') | Categórico Binário |
| ('P7_d_4 ', 'Utilizando API's para extrair dados e complementar minhas análises.') | Categórico Binário |
| ('P7_d_5 ', 'Realizando experimentos e estudos utilizando metodologias estatísticas como teste de hipótese, modelos de regressão etc.') | Categórico Binário |
| ('P7_d_6 ', 'Desenvolvendo/cuidando da manutenção de ETL's utilizando tecnologias como Talend, Pentaho, Airflow, Dataflow etc.') | Categórico Binário |
| ('P7_d_7 ', 'Atuando na modelagem dos dados, com o objetivo de criar conjuntos de dados, Data Warehouses, Data Marts etc.') | Categórico Binário |
| ('P7_d_8 ', 'Desenvolvendo/cuidando da manutenção de planilhas do Excel ou Google Sheets para atender as áreas de negócio.') | Categórico Binário |
| ('P7_d_9 ', 'Utilizando ferramentas avançadas de estatística como SAS, SPSS, Stata etc, para realizar análises.') | Categórico Binário |
| ('P7_d_10 ', 'Nenhuma das opções listadas refletem meu dia a dia.') | Categórico Binário |
| ('P8_a ', 'Quais das opções abaixo fazem parte da sua rotina no trabalho atual com ciência de dados?') | Categórico Polinomial Não Ordinal |
| ('P8_a_1 ', 'Estudos Ad-hoc com o objetivo de confirmar hipóteses, realizar modelos preditivos, forecasts, análise de cluster para resolver problemas pontuais e responder perguntas das áreas de negócio.') | Categórico Binário |
| ('P8_a_2 ', 'Sou responsável pela coleta e limpeza dos dados que uso para análise e modelagem.') | Categórico Binário |
| ('P8_a_3 ', 'Sou responsável por entrar em contato com os times de negócio para definição do problema, identificar a solução e apresentação de resultados.') | Categórico Binário |
| ('P8_a_4 ', 'Desenvolvo modelos de Machine Learning com o objetivo de colocar em produção em sistemas (produtos de dados).') | Categórico Binário |
| ('P8_a_5 ', 'Sou responsável por colocar modelos em produção, criar os pipelines de dados, APIs de consumo e monitoramento.') | Categórico Binário |
| ('P8_a_6 ', 'Cuido da manutenção de modelos de Machine Learning já em produção, atuando no monitoramento, ajustes e refatoração quando necessário.') | Categórico Binário |
| ('P8_a_7 ', 'Realizo construções de dashboards em ferramentas de BI como PowerBI, Tableau, Looker, Qlik, etc') | Categórico Binário |
| ('P8_a_8 ', 'Utilizo ferramentas avançadas de estatística como SAS, SPSS, Stata etc, para realizar análises estatísticas e ajustar modelos.') | Categórico Binário |
| ('P8_a_9 ', 'Crio e dou manutenção em ETLs, DAGs e automações de pipelines de dados.') | Categórico Binário |
| ('P8_a_10 ', 'Crio e gerencio soluções de Feature Store e cultura de MLOps.') | Categórico Binário |
| ('P8_a_11 ', 'Sou responsável por criar e manter a infra que meus modelos e soluções rodam (clusters, servidores, API, containers, etc.)') | Categórico Binário |
| ('P8_a_12 ', 'Treino e aplico LLM's para solucionar problemas de negócio.') | Categórico Binário |
| ('P8_b ', 'Quais as técnicas e métodos listados abaixo você costuma utilizar no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P8_b_1 ', 'Utilizo modelos de regressão (linear, logística, GLM)') | Categórico Binário |
| ('P8_b_2 ', 'Utilizo redes neurais ou modelos baseados em árvore para criar modelos de classificação') | Categórico Binário |
| ('P8_b_3 ', 'Desenvolvo sistemas de recomendação (RecSys)') | Categórico Binário |
| ('P8_b_4 ', 'Utilizo métodos estatísticos Bayesianos para analisar dados') | Categórico Binário |
| ('P8_b_5 ', 'Utilizo técnicas de NLP (Natural Language Processing) para análisar dados não-estruturados') | Categórico Binário |
| ('P8_b_6 ', 'Utilizo métodos estatísticos clássicos (Testes de hipótese, análise multivariada, sobrevivência, dados longitudinais, inferência estatistica) para analisar dados') | Categórico Binário |
| ('P8_b_7 ', 'Utilizo cadeias de Markov ou HMM's para realizar análises de dados') | Categórico Binário |
| ('P8_b_8 ', 'Desenvolvo técnicas de Clusterização (K-means, Spectral, DBScan etc)') | Categórico Binário |
| ('P8_b_9 ', 'Realizo previsões através de modelos de Séries Temporais (Time Series)') | Categórico Binário |
| ('P8_b_10 ', 'Utilizo modelos de Reinforcement Learning (aprendizado por reforço)') | Categórico Binário |
| ('P8_b_11 ', 'Utilizo modelos de Machine Learning para detecção de fraude') | Categórico Binário |
| ('P8_b_12 ', 'Utilizo métodos de Visão Computacional') | Categórico Binário |
| ('P8_b_13 ', 'Utilizo modelos de Detecção de Churn') | Categórico Binário |
| ('P8_b_14 ', 'Utilizo LLM's para solucionar problemas de negócio') | Categórico Binário |
| ('P8_3 ', 'Quais dessas tecnologias fazem parte do seu dia a dia como cientista de dados?') | Categórico Polinomial Não Ordinal |
| ('P8_c_1 ', 'Ferramentas de BI (PowerBI, Looker, Tableau, Qlik etc)') | Categórico Binário |
| ('P8_c_2 ', 'Planilhas (Excel, Google Sheets etc)') | Categórico Binário |
| ('P8_c_3 ', 'Ambientes de desenvolvimento local (R-studio, JupyterLab, Anaconda)') | Categórico Binário |
| ('P8_c_4 ', 'Ambientes de desenvolvimento na nuvem (Google Colab, AWS Sagemaker, Kaggle Notebooks etc)') | Categórico Binário |
| ('P8_c_5 ', 'Ferramentas de AutoML (Datarobot, H2O, Auto-Keras etc)') | Categórico Binário |
| ('P8_c_6 ', 'Ferramentas de ETL (Apache Airflow, NiFi, Stitch, Fivetran, Pentaho etc)') | Categórico Binário |
| ('P8_c_7 ', 'Plataformas de Machine Learning (TensorFlow, Azure Machine Learning, Kubeflow etc)') | Categórico Binário |
| ('P8_c_8 ', 'Feature Store (Feast, Hopsworks, AWS Feature Store, Databricks Feature Store etc)') | Categórico Binário |
| ('P8_c_9 ', 'Sistemas de controle de versão (Github, DVC, Neptune, Gitlab etc)') | Categórico Binário |
| ('P8_c_10 ', 'Plataformas de Data Apps (Streamlit, Shiny, Plotly Dash etc)') | Categórico Binário |
| ('P8_c_11 ', 'Ferramentas de estatística avançada como SPSS, SAS, etc.') | Categórico Binário |
| ('P8_d ', 'Em qual das opções abaixo você gasta a maior parte do seu tempo no trabalho?') | Categórico Polinomial Não Ordinal |
| ('P8_d_1 ', 'Estudos Ad-hoc com o objetivo de confirmar hipóteses, realizar modelos preditivos, forecasts, análise de cluster para resolver problemas pontuais e responder perguntas das áreas de negócio.') | Categórico Binário |
| ('P8_d_2 ', 'Coletando e limpando os dados que uso para análise e modelagem.') | Categórico Binário |
| ('P8_d_3 ', 'Entrando em contato com os times de negócio para definição do problema, identificar a solução e apresentação de resultados.') | Categórico Binário |
| ('P8_d_4 ', 'Desenvolvendo modelos de Machine Learning com o objetivo de colocar em produção em sistemas (produtos de dados).') | Categórico Binário |
| ('P8_d_5 ', 'Colocando modelos em produção, criando os pipelines de dados, APIs de consumo e monitoramento.') | Categórico Binário |
| ('P8_d_6 ', 'Cuidando da manutenção de modelos de Machine Learning já em produção, atuando no monitoramento, ajustes e refatoração quando necessário.') | Categórico Binário |
| ('P8_d_7 ', 'Realizando construções de dashboards em ferramentas de BI como PowerBI, Tableau, Looker, Qlik, etc.') | Categórico Binário |
| ('P8_d_8 ', 'Utilizando ferramentas avançadas de estatística como SAS, SPSS, Stata etc, para realizar análises.') | Categórico Binário |
| ('P8_d_9 ', 'Criando e dando manutenção em ETLs, DAGs e automações de pipelines de dados.') | Categórico Binário |
| ('P8_d_10 ', 'Criando e gerenciando soluções de Feature Store e cultura de MLOps.') | Categórico Binário |
| ('P8_d_11 ', 'Criando e mantendo a infra que meus modelos e soluções rodam (clusters, servidores, API, containers, etc.)') | Categórico Binário |
| ('P8_d_12 ', 'Treinando e aplicando LLM's para solucionar problemas de negócio.') | Categórico Binário |
</details>

#### `PNAD_Roubos_Furtos_Brasil_2023`

Esta base de dados contém informações agregadas sobre ocorrências de roubos e furtos no Brasil, organizadas por grande região. Os dados abrangem diferentes categorias de ocorrência, como roubos de veículos, em domicílios e em locais públicos, possibilitando uma análise do perfil e distribuição regional desses eventos. Essa base pode ser utilizada para identificar padrões territoriais de criminalidade patrimonial, auxiliando em estudos sobre segurança pública e desigualdades regionais.

- Atributos da Base

| Atributo             | Tipo                  | Descrição |
|----------------------|-----------------------|-----------|
| Grande Região        | Categórico Nominal    | Região do Brasil onde o crime ocorreu (Sudeste, Nordeste, Norte, Sul, Centro-Oeste) |
| Veículo              | Quantitativo Discreto | Total de ocorrências envolvendo qualquer tipo de veículo |
| Carro                | Quantitativo Discreto | Total de ocorrências envolvendo carros |
| Moto                 | Quantitativo Discreto | Total de ocorrências envolvendo motos |
| Bicicleta            | Quantitativo Discreto | Total de ocorrências envolvendo bicicletas |
| Domicílio            | Quantitativo Discreto | Total de ocorrências registradas em residências |
| Fora do domicílio    | Quantitativo Discreto | Total de ocorrências em locais públicos ou externos |

#### `PNAD Média Horas Semanais de Trabalho Doméstico por Cor ou Raça - Brasil`

Esta base de dados apresenta a média de horas semanais dedicadas ao trabalho doméstico por diferentes grupos raciais no Brasil. Os dados são úteis para identificar desigualdades na distribuição do trabalho não remunerado e suas possíveis relações com raça/cor.

- Atributos da Base

| Atributo     | Tipo                   | Dados                        |
|--------------|------------------------|------------------------------|
| Cor ou raça  | Categórico Nominal     | Branca; Preta; Parda; Total |
| Total        | Quantitativo Contínuo  | Horas semanais (ex: 17,4)   |


###    Descrição de dados

### `Análise Exploratória dos Dados - State_of_data_BR_2023_Kaggle - df_survey_2023`

#### 1. Distribuição por Gênero

- **Moda:** Masculino (3975 respostas)
- **Distribuição:**
  - Feminino: **24,46%**
  - Masculino: **75,23%**
  - Outro: **0,17%**
  - Prefiro não informar: **0,30%**
    
![genero](https://github.com/user-attachments/assets/3df947d6-bf29-48f3-a2ff-c1cdfeaa71be)

#### 2. Pessoas com Deficiência (PCD)

- **Moda:** Não (5156 respostas)
- **Distribuição:**
  - Não: **97,22%**
  - Prefiro não informar: **0,49%**
  - Sim: **2,09%**
    
![pcd](https://github.com/user-attachments/assets/dc9d3912-e8c3-436f-a168-727c6a638f13)

#### 3. Estado de Residência

- **Moda:** São Paulo (2073 respostas)
- **Estados com maior representação:**
  - São Paulo (SP): **39,42%**
  - Minas Gerais (MG): **10,59%**
  - Rio de Janeiro (RJ): **8,31%**
  - Paraná (PR): **7,99%**
  - Rio Grande do Sul (RS): **5,54%**
 
![Estado](https://github.com/user-attachments/assets/69bdc86a-2929-417c-838f-3f1a2e3c4a64)

#### 4. Nível Profissional

- **Moda:** Sênior (1419 respostas)
- **Distribuição:**
  - Júnior: **27,46%**
  - Pleno: **36,56%**
  - Sênior: **36,98%**
 
![Nivel](https://github.com/user-attachments/assets/d760284c-8ba4-484a-813a-3e1ed06a9e58)

#### 5. Faixa Salarial

- **Moda:** de R$ 8.001/mês a R$ 12.000/mês (1026 respostas)
- **Faixas com maior representação:**
  - R$ 8.001 a R$ 12.000: **18,85%**
  - R$ 12.001 a R$ 16.000: **11,95%**
  - R$ 4.001 a R$ 6.000: **13,68%**
  - R$ 6.001 a R$ 8.000: **11,71%**

![salario](https://github.com/user-attachments/assets/fd0ad9d4-b767-4fb6-a390-d8245c6c268d)

#### 6. Forma de Trabalho Atual

- **Moda:** Modelo 100% remoto (2201 respostas)
- **Distribuição:**
  - Modelo 100% presencial: **14,91%**
  - Modelo 100% remoto: **41,58%**
  - Modelo híbrido com dias fixos: **14,91%**
  - Modelo híbrido flexível: **18,38%**

![FormaTrabalho](https://github.com/user-attachments/assets/786e5481-844d-4005-bb91-a9e45279475b)

#### 7. Forma de Trabalho Ideal

- **Moda:** Modelo híbrido flexível (2144 respostas)
- **Distribuição:**
  - Modelo 100% presencial: **1,81%**
  - Modelo 100% remoto: **40,27%**
  - Modelo híbrido com dias fixos: **7,37%**
  - Modelo híbrido flexível: **40,69%**

![formaIdeal](https://github.com/user-attachments/assets/6621eb7f-6d8c-4c6c-b494-f6fb14dffb8d)

#### **1. Comparação entre Nível Profissional e Forma de Trabalho**

- **Moda:** Profissionais **Sêniores** preferem o modelo **100% remoto** (**796 respostas**), enquanto os **Plenos** também escolhem majoritariamente o **100% remoto** (**673 respostas**). Já os **Júniores** têm uma distribuição mais equilibrada entre **100% remoto** (395 respostas) e **100% presencial** (283 respostas).  

##### **Distribuição dentro de cada Nível Profissional**  

- **Sênior**  
  - **100% presencial:** **9,02%** (128)  
  - **100% remoto:** **56,08%** (796)  
  - **Híbrido fixo:** **14,52%** (206)  
  - **Híbrido flexível:** **20,36%** (289)  

- **Pleno**  
  - **100% presencial:** **16,10%** (224)  
  - **100% remoto:** **48,35%** (673)  
  - **Híbrido fixo:** **17,11%** (238)  
  - **Híbrido flexível:** **18,47%** (257)  

- **Júnior**  
  - **100% presencial:** **27,06%** (283)  
  - **100% remoto:** **37,75%** (395)  
  - **Híbrido fixo:** **17,78%** (186)  
  - **Híbrido flexível:** **17,41%** (182)  

- **Não informado**  
  - **100% presencial:** **17,30%** (155)  
  - **100% remoto:** **37,61%** (337)  
  - **Híbrido fixo:** **17,86%** (160)  
  - **Híbrido flexível:** **27,23%** (244)  

![NivelXmodelo](https://github.com/user-attachments/assets/cf59df5f-0648-4393-8ebf-68c8e2d18607)

#### **2. Comparação entre Estados e Forma de Trabalho**  

- **Moda:** O modelo **100% remoto** é o mais comum em todos os estados, sendo **São Paulo (SP)** o que mais concentra profissionais nesse modelo (**759 respostas**), seguido por **Minas Gerais (MG) (252 respostas)** e **Rio de Janeiro (RJ) (194 respostas)**.   

##### **Distribuição por Estado (%)**  

###### **São Paulo (SP)**  
- **100% presencial:** **11,29%** (214)  
- **100% remoto:** **40,06%** (759)  
- **Híbrido fixo:** **22,48%** (426)  
- **Híbrido flexível:** **26,17%** (496)  

###### **Minas Gerais (MG)**  
- **100% presencial:** **17,46%** (88)  
- **100% remoto:** **50,00%** (252)  
- **Híbrido fixo:** **12,50%** (63)  
- **Híbrido flexível:** **20,04%** (101)  

###### **Rio de Janeiro (RJ)**  
- **100% presencial:** **11,36%** (45)  
- **100% remoto:** **48,99%** (194)  
- **Híbrido fixo:** **18,94%** (75)  
- **Híbrido flexível:** **20,71%** (82)  

###### **Paraná (PR)**  
- **100% presencial:** **21,54%** (84)  
- **100% remoto:** **51,03%** (199)  
- **Híbrido fixo:** **15,64%** (61)  
- **Híbrido flexível:** **11,79%** (46)  

###### **Rio Grande do Sul (RS)**  
- **100% presencial:** **18,70%** (49)  
- **100% remoto:** **48,85%** (128)  
- **Híbrido fixo:** **8,40%** (22)  
- **Híbrido flexível:** **24,05%** (63)  

###### **Santa Catarina (SC)**  
- **100% presencial:** **15,38%** (36)  
- **100% remoto:** **50,85%** (119)  
- **Híbrido fixo:** **13,25%** (31)  
- **Híbrido flexível:** **20,51%** (48)  

###### **Distrito Federal (DF)**  
- **100% presencial:** **23,02%** (35)  
- **100% remoto:** **43,42%** (66)  
- **Híbrido fixo:** **19,74%** (30)  
- **Híbrido flexível:** **13,82%** (21)  

![EstadoXmodelo](https://github.com/user-attachments/assets/69b4db17-d1e1-41a0-8338-d0bd773d0eca)

#### **3. Comparação entre Faixa Salarial e Modelo de Trabalho**  

- **Moda:** O modelo **100% remoto** se destaca nas faixas salariais mais altas, especialmente **acima de R$ 8.000/mês**. Já o modelo **100% presencial** tem maior concentração em salários **abaixo de R$ 6.000/mês**.  

##### **Distribuição por Faixa Salarial (%)**  

###### **Faixa: R$ 8.001/mês a R$ 12.000/mês**  
- **100% presencial:** **11,02%** (113)  
- **100% remoto:** **51,08%** (524)  
- **Híbrido fixo:** **17,45%** (179)  
- **Híbrido flexível:** **20,45%** (210)  

###### **Faixa: R$ 4.001/mês a R$ 6.000/mês**  
- **100% presencial:** **21,61%** (161)  
- **100% remoto:** **41,61%** (310)  
- **Híbrido fixo:** **20,13%** (150)  
- **Híbrido flexível:** **16,64%** (124)  

###### **Faixa: R$ 12.001/mês a R$ 16.000/mês**  
- **100% presencial:** **6,77%** (44)  
- **100% remoto:** **56,00%** (364)  
- **Híbrido fixo:** **12,92%** (84)  
- **Híbrido flexível:** **24,31%** (158)  

###### **Faixa: R$ 6.001/mês a R$ 8.000/mês**  
- **100% presencial:** **13,50%** (86)  
- **100% remoto:** **45,68%** (291)  
- **Híbrido fixo:** **16,64%** (106)  
- **Híbrido flexível:** **24,18%** (154)  

###### **Faixa: R$ 3.001/mês a R$ 4.000/mês**  
- **100% presencial:** **32,39%** (114)  
- **100% remoto:** **33,81%** (119)  
- **Híbrido fixo:** **20,45%** (72)  
- **Híbrido flexível:** **13,35%** (47)  

###### **Faixa: R$ 16.001/mês a R$ 20.000/mês**  
- **100% presencial:** **7,92%** (26)  
- **100% remoto:** **53,66%** (176)  
- **Híbrido fixo:** **17,38%** (57)  
- **Híbrido flexível:** **21,04%** (69)  

###### **Faixa: R$ 2.001/mês a R$ 3.000/mês**  
- **100% presencial:** **39,93%** (115)  
- **100% remoto:** **30,56%** (88)  
- **Híbrido fixo:** **16,32%** (47)  
- **Híbrido flexível:** **13,19%** (38)  

###### **Faixa: R$ 1.001/mês a R$ 2.000/mês**  
- **100% presencial:** **35,81%** (77)  
- **100% remoto:** **36,28%** (78)  
- **Híbrido fixo:** **13,95%** (30)  
- **Híbrido flexível:** **13,95%** (30)  

###### **Faixa: Acima de R$ 25.000/mês**  
- **100% presencial:** **14,28%** (35)  
- **100% remoto:** **51,42%** (126)  
- **Híbrido fixo:** **17,14%** (42)  
- **Híbrido flexível:** **17,14%** (42)  

![SalarioXmodelo](https://github.com/user-attachments/assets/0cbda8e9-5f41-4ef6-8e88-ff2f3673124c)


### Análise Exploratória dos Dados - PNAD Roubos e Furtos (Brasil)

Este documento apresenta a análise exploratória dos dados da PNAD sobre roubos e furtos no Brasil, organizados por grande região e por tipo de ocorrência (veículos, carros, motos, bicicletas, domicílios e fora do domicílio). O objetivo é identificar padrões regionais e categorias mais recorrentes.

#### 1. Total de Ocorrências por Região (Soma Geral)

- **Moda:** Sudeste (814 ocorrências)
- **Distribuição percentual:**
  - Sudeste: **32,64%**
  - Nordeste: **29,41%**
  - Norte: **11,44%**
  - Sul: **5,21%**
  - Centro-Oeste: **5,17%**

![Soma](https://github.com/user-attachments/assets/cf308f76-285a-430b-9e39-2ac119e8c1b3)

#### 2. Ocorrências por Categoria e Região

- **Categoria mais frequente no geral:** Fora do domicílio (1398 ocorrências)
- **Categorias com maior concentração por região:**
  - Sudeste: Fora do domicílio (565 ocorrências)
  - Nordeste: Fora do domicílio (487 ocorrências)
  - Norte: Fora do domicílio (190 ocorrências)
  - Sul: Fora do domicílio (74 ocorrências)
  - Centro-Oeste: Fora do domicílio (82 ocorrências)

![SomaCategoria](https://github.com/user-attachments/assets/37ef8272-211b-43e1-adb9-35dd1358c3d5)

#### 3. Domicílio x Fora do Domicílio por Região

- **Moda:** Fora do domicílio em todas as regiões
- **Distribuição total:**
  - Domicílio: **195 ocorrências**
  - Fora do domicílio: **1398 ocorrências**

![DomicilioXforaDomicilio](https://github.com/user-attachments/assets/9114ae1b-2fef-48a2-9c5b-56b1c4eb9012)


### Análise Exploratória dos Dados - PNAD Média Horas de Trabalho Doméstico por Cor ou Raça (Brasil)

Este documento apresenta uma análise exploratória sobre o tempo médio semanal dedicado ao trabalho doméstico, categorizado por cor ou raça no Brasil. Os dados analisados permitem observar disparidades sutis, mas relevantes, que refletem aspectos sociais e estruturais presentes na divisão de tarefas não remuneradas.

#### 1. Horas Semanais de Trabalho Doméstico por Cor ou Raça
- **Média Geral:** 17 horas/semana
- **Distribuição por grupo racial:**
  - **Branca:** 16,5 horas
  - **Preta:** 17,1 horas
  - **Parda:** 17,4 horas
  
![HorasDomesticas](https://github.com/user-attachments/assets/e3e3678b-dee1-47b5-8a7e-29c5c2a3e049)


## Preparação dos dados

A preparação dos dados consiste dos seguintes passos:

### Seleção de Atributos:
#### `State_of_data_BR_2023_Kaggle - df_survey_2023`
* ('P1_b ', 'Genero')
* ('P1_d ', 'PCD')
* ('P1_i ', 'Estado onde mora')
* ('P2_f ', 'Cargo Atual')
* ('P2_g ', 'Nivel')
* ('P2_h ', 'Faixa salarial')
* ('P2_o_4 ', 'Flexibilidade de trabalho remoto')
* ('P2_r ', 'Atualmente qual a sua forma de trabalho?')
* ('P2_s ', 'Qual a forma de trabalho ideal para você?')

#### `PNAD_Roubos_Furtos - df_roubos_furtos`
* ('Grande Região', 'Região geográfica do Brasil')
* ('Veículo', 'Ocorrências de roubo/furto de veículos em geral')
* ('Carro', 'Ocorrências de roubo/furto de carros')
* ('Moto', 'Ocorrências de roubo/furto de motos')
* ('Bicicleta', 'Ocorrências de roubo/furto de bicicletas')
* ('Domicílio', 'Ocorrências de roubo/furto dentro do domicílio')
* ('Fora do domicílio', 'Ocorrências de roubo/furto fora do domicílio')
* ('Soma', 'Total de ocorrências registradas por região')

#### `PNAD_Tempo_Trab_Doméstico - df_trabalho_domestico`

* ('Cor ou raça', 'Grupo racial da pessoa entrevistada')
* ('Total', 'Quantidade média de horas semanais dedicadas ao trabalho doméstico')

## Indução de modelos

### Modelo 1: árvore de decisão

### Importção de Bibliotecas
```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, classification_report, confusion_matrix
from sklearn.feature_extraction import DictVectorizer
from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import train_test_split
import matplotlib.pyplot as plt
```
### Importação do dataset
```python
df = pd.read_csv("dataset_tratado.csv")

print("\nDimensões:", df.shape)
print("\nCampos:", df.columns)
print(df.describe())
```
```
Dimensões: (3713, 24)

Campos: Index(['Idade', 'Gênero', 'Cor/Raça', 'Horas com trabalho doméstico e cuidado',
       'PCD', 'Estado onde mora', 'Região onde mora', 'Roubos de veículo',
       'Roubos de carro', 'Roubos de moto', 'Roubos de bicicleta',
       'Roubos fora do domicílio', 'Total de roubos', 'Nivel de segurança',
       'Nível de ensino', 'Área de formação', 'Situação atual de trabalho',
       'Cargo atual', 'Nível', 'Faixa salarial', 'Tempo de experiência',
       'Forma de trabalho atual',
       'Decisão da empresa para modelo 100% presencial',
       'Forma de trabalho ideal'],
      dtype='object')
             Idade  Horas com trabalho doméstico e cuidado  Roubos de veículo  \
count  3713.000000                             3713.000000        3713.000000   
mean     30.887692                               16.787988          68.710477   
std       6.843938                                0.394420          34.970815   
min      18.000000                               16.500000          12.000000   
25%      26.000000                               16.500000          12.000000   
50%      29.000000                               16.500000          92.000000   
75%      34.000000                               17.400000          92.000000   
max      70.000000                               17.400000          92.000000   

       Roubos de carro  Roubos de moto  Roubos de bicicleta  \
count      3713.000000     3713.000000          3713.000000   
mean         45.747374       22.914894            16.683275   
std          26.831917       15.235800             8.925420   
min           8.000000        3.000000             2.000000   
25%          10.000000        4.000000             3.000000   
50%          67.000000       25.000000            23.000000   
75%          67.000000       25.000000            23.000000   
max          67.000000       57.000000            23.000000   

       Roubos fora do domicílio  Total de roubos  
count               3713.000000      3713.000000  
mean                 422.008080       559.380824  
std                  212.668114       282.446508  
min                   74.000000        98.000000  
25%                   82.000000       107.000000  
50%                  565.000000       749.000000  
75%                  565.000000       749.000000  
max                  565.000000       749.000000 
```
### Transformando os dados
```python
# Separar variáveis independentes e alvo
X_dict = df.drop(columns=['Roubos de veículo', 'Roubos de carro', 'Roubos de moto', 'Roubos de bicicleta', 'Roubos fora do domicílio', 'Total de roubos', 'Forma de trabalho ideal']).to_dict(orient='records')
vect = DictVectorizer(sparse=False)
X = vect.fit_transform(X_dict)

le = LabelEncoder()
y = le.fit_transform(df['Forma de trabalho ideal'])

# Dividir os dados corretamente
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

print("Shape dos dados de treino:", X_train.shape)
print("Shape dos dados de teste:", X_test.shape)
```
```
Shape dos dados de treino: (2599, 117)
Shape dos dados de teste: (1114, 117)
```
### Indução do Modelo
```python
from sklearn.metrics import ConfusionMatrixDisplay
from matplotlib import pyplot as plt

# Definir modelo com limitação de profundidade e folhas mínimas
treeForma = DecisionTreeClassifier(random_state=42, criterion='entropy', max_depth=7)
treeForma.fit(X_train, y_train)
print("Acurácia no treino:", treeForma.score(X_train, y_train))

# Avaliação no conjunto de teste
y_pred = treeForma.predict(X_test)
print("Acurácia no teste:", accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))
cnf_matrix = confusion_matrix(y_test, y_pred)
cnf_table = pd.DataFrame(cnf_matrix, index=[f"Real={c}" for c in le.classes_], columns=[f"Prev={c}" for c in le.classes_])
print(cnf_table)

display = ConfusionMatrixDisplay.from_estimator(treeForma, X_test, y_test, display_labels=le.classes_, cmap=plt.cm.Blues)

plt.xticks(rotation=90)
plt.show()
```
```
Acurácia no treino: 0.7933820700269334
Acurácia no teste: 0.7459605026929982
              precision    recall  f1-score   support

           0       0.14      0.05      0.08        19
           1       0.74      0.77      0.75       524
           2       0.76      0.75      0.76       571

    accuracy                           0.75      1114
   macro avg       0.55      0.52      0.53      1114
weighted avg       0.74      0.75      0.74      1114

                             Prev=Modelo 100% presencial  \
Real=Modelo 100% presencial                            1   
Real=Modelo 100% remoto                                4   
Real=Modelo híbrido                                    2   

                             Prev=Modelo 100% remoto  Prev=Modelo híbrido  
Real=Modelo 100% presencial                        3                   15  
Real=Modelo 100% remoto                          401                  119  
Real=Modelo híbrido                              140                  429 
```
![image](https://github.com/user-attachments/assets/40653726-2954-4eae-9eb9-f171b6958a2e)
### Exibição da Importância dos Atributos 
```python
# Exibir importâncias dos atributos
importances = pd.Series(treeForma.feature_importances_, index=vect.feature_names_)
importances = importances[importances > 0].sort_values(ascending=False).head(10)
print("\nImportância dos atributos:")
print(importances)

# Visualizar graficamente
importances.plot(kind='barh', figsize=(10, 6), title='Importância dos Atributos')
plt.gca().invert_yaxis()
plt.show()
```
```
Importância dos atributos:
Decisão da empresa para modelo 100% presencial=Vou procurar outra oportunidade no modelo 100% remoto    0.542008
Forma de trabalho atual=Modelo 100% remoto                                                              0.138466
Idade                                                                                                   0.044985
Tempo de experiência=de 7 a 10 anos                                                                     0.015375
Estado onde mora=Rio Grande do Sul (RS)                                                                 0.014193
Nível=Pleno                                                                                             0.011914
Situação atual de trabalho=Empregado (CLT)                                                              0.011717
Decisão da empresa para modelo 100% presencial=Vou aceitar e retornar ao modelo 100% presencial         0.010651
Estado onde mora=Distrito Federal (DF)                                                                  0.010012
Cargo atual=Analista de Negócios/Business Analyst                                                       0.009890
dtype: float64
```
![image](https://github.com/user-attachments/assets/3a1a1457-6de5-44cc-bd80-16940ce4c4a0)
### Exibição da Árvore de Decisão
```python
import pydotplus
from sklearn import tree
from IPython.display import Image

dot_data = tree.export_graphviz(treeForma, out_file=None, feature_names=vect.get_feature_names_out(), class_names=le.classes_, filled=True, rounded=True, special_characters=True)

graph = pydotplus.graph_from_dot_data(dot_data)
Image(graph.create_png())
```
![image](https://github.com/user-attachments/assets/2c49d63e-32e1-451b-80ce-e9e0275cb7cb)
### Modelo 2: Random Forest

### Importação das bibliotecas e do dataset
Importa a biblioteca pandas, carrega a base de dados CSV a partir do Google Drive e exibe as primeiras 5 linhas da tabela para visualização.
```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
from sklearn.preprocessing import LabelEncoder
from sklearn.feature_extraction import DictVectorizer

data = pd.read_csv('dataset_tratado.csv')

pd.set_option('display.max_columns', None)

print(f'Dimensões: {data.shape}')
print(f'Colunas: {data.columns}')

data.head(5)
```
### Gerando base de treinamento e teste
Seleciona os dados de teste e o alvo e codifica os valores categóricos para numéricos e divide a base de dados em treino (70%) e teste (30%)
```python
X_dict = data.drop(columns=['Roubos de veículo', 'Roubos de carro', 'Roubos de moto', 'Roubos de bicicleta', 'Roubos fora do domicílio', 'Total de roubos', 'Forma de trabalho ideal'], axis=1).T.to_dict().values()
vect = DictVectorizer(sparse=False)
X = vect.fit_transform(X_dict)

le = LabelEncoder()
y = le.fit_transform(data.iloc[:, data.shape[1]-1])

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```
### Treinando o Random Forest
Treina o RandomForest e guarda todas as acurácias em um array, foi separado duas árvores para fins de comparação. Uma com melhor desempenho de acurácia e outra com o pior desempenho
```python
forest = RandomForestClassifier(random_state=42, criterion='entropy', max_depth=7)
forest.fit(X_train, y_train)
print(f'Acurácia do treinamento: {forest.score(X_train, y_train)}')

accuracies = {}

for i, tree_model in enumerate(forest.estimators_):
  y_pred = tree_model.predict(X_test)
  acc_score = accuracy_score(y_test, y_pred)
  accuracies[i] = acc_score

best_tree = max(accuracies, key=accuracies.get)
worst_tree = min(accuracies, key=accuracies.get)

print(f'Acurácia da melhor árvore: {accuracies[best_tree]}')
print(f'Acurácia da pior árvore: {accuracies[worst_tree]}')

best_y_pred = forest.estimators_[best_tree].predict(X_test)
worst_y_pred = forest.estimators_[worst_tree].predict(X_test)

print('\nClassification Report da melhor árvore:')
print(classification_report(y_test, best_y_pred))
print('\nClassification Report da pior árvore:')
print(classification_report(y_test, worst_y_pred))
```
```
Acurácia do treinamento: 0.8260869565217391
Acurácia da melhor árvore: 0.7630161579892281
Acurácia da pior árvore: 0.5915619389587073

Classification Report da melhor árvore:
              precision    recall  f1-score   support

           0       0.00      0.00      0.00        19
           1       0.82      0.68      0.74       524
           2       0.73      0.87      0.79       571

    accuracy                           0.76      1114
   macro avg       0.52      0.51      0.51      1114
weighted avg       0.76      0.76      0.76      1114


Classification Report da pior árvore:
              precision    recall  f1-score   support

           0       0.00      0.00      0.00        19
           1       0.59      0.55      0.57       524
           2       0.60      0.65      0.62       571

    accuracy                           0.59      1114
   macro avg       0.40      0.40      0.40      1114
weighted avg       0.58      0.59      0.59      1114
```
### Matriz de confusão da melhor árvore
Aqui foi feita a visualização da matriz de confusão da árvore com melhor desempenho, sendo mostrado uma pequena confusão entre remoto e hibrído. O modelo presencial foi completamente desconsiderado em função de ter poucos dados relacionados a esse modelo
```python
from sklearn.metrics import ConfusionMatrixDisplay
from matplotlib import pyplot as plt

# Melhor arvore
best_cnf_matrix = confusion_matrix(y_test, best_y_pred)
print(f'Matriz de confusão: \n{best_cnf_matrix}')

df_cnf_matrix = pd.DataFrame(best_cnf_matrix, index=le.classes_, columns=le.classes_)
print(f'Matriz de confusão formatada: \n{df_cnf_matrix}')

display = ConfusionMatrixDisplay.from_estimator(forest.estimators_[best_tree], X_test, y_test, display_labels=le.classes_, cmap=plt.cm.Greens)

plt.xticks(rotation=90)
plt.show()
```
```
Matriz de confusão: 
[[  0   1  18]
 [  2 356 166]
 [  1  76 494]]
Matriz de confusão formatada: 
                        Modelo 100% presencial  Modelo 100% remoto  \
Modelo 100% presencial                       0                   1   
Modelo 100% remoto                           2                 356   
Modelo híbrido                               1                  76   

                        Modelo híbrido  
Modelo 100% presencial              18  
Modelo 100% remoto                 166  
Modelo híbrido                     494  
```
![image](https://github.com/user-attachments/assets/7a692d74-e83f-41c1-87fd-4353d81c79f6)
### Matriz de confusão da pior árvore
Enquanto aqui, é descrito a matriz de confusão da da árvore com menor desempenho. Aqui a confusão entre hibrido e remoto é mais generalizada
```python
from sklearn.metrics import ConfusionMatrixDisplay
from matplotlib import pyplot as plt

# Melhor arvore
worst_cnf_matrix = confusion_matrix(y_test, worst_y_pred)
print(f'Matriz de confusão: \n{best_cnf_matrix}')

df_cnf_matrix = pd.DataFrame(worst_cnf_matrix, index=le.classes_, columns=le.classes_)
print(f'Matriz de confusão formatada: \n{df_cnf_matrix}')

display = ConfusionMatrixDisplay.from_estimator(forest.estimators_[worst_tree], X_test, y_test, display_labels=le.classes_, cmap=plt.cm.Greens)

plt.xticks(rotation=90)
plt.show()
```
```
Matriz de confusão: 
[[  0   1  18]
 [  2 356 166]
 [  1  76 494]]
Matriz de confusão formatada: 
                        Modelo 100% presencial  Modelo 100% remoto  \
Modelo 100% presencial                       0                   1   
Modelo 100% remoto                           1                 290   
Modelo híbrido                               4                 198   

                        Modelo híbrido  
Modelo 100% presencial              18  
Modelo 100% remoto                 233  
Modelo híbrido                     369  
```
![image](https://github.com/user-attachments/assets/e6bd93ce-b71d-4b2b-a944-9ae2a6525fc6)
### Visualização de um gráfico de importância da melhor árvore
Foi feito uma vizualização dos valores mais importantes na construção da melhor árvore. Os atributos mais importantes levam em consideração a forma de trabalho atual do profissional e a atitude do profissional caso a empresa adote o modelo 100% presencial
```python
best_importance = forest.estimators_[best_tree].feature_importances_

best_importance_series = pd.Series(best_importance, index=vect.get_feature_names_out())
best_importance_series = best_importance_series.sort_values(ascending=False).head(10)

print(f'Importância das variáveis: \n{best_importance_series}')

plt.figure(figsize=(5, 5))
best_importance_series.plot(kind='barh', legend=False)
plt.title('Importância das variáveis (Melhor árvore)')
plt.gca().invert_yaxis()
```
```
Importância das variáveis: 
Decisão da empresa para modelo 100% presencial=Vou aceitar e retornar ao modelo 100% presencial               0.311739
Forma de trabalho atual=Modelo híbrido                                                                        0.212135
Decisão da empresa para modelo 100% presencial=Vou procurar outra oportunidade no modelo híbrido ou remoto    0.096771
Decisão da empresa para modelo 100% presencial=Vou procurar outra oportunidade no modelo 100% remoto          0.085514
Forma de trabalho atual=Modelo 100% remoto                                                                    0.064423
Área de formação=Outra opção                                                                                  0.014356
Faixa salarial=de R$ 4.001/mês a R$ 6.000/mês                                                                 0.013847
Nível=Sênior                                                                                                  0.011894
Estado onde mora=Rio Grande do Sul (RS)                                                                       0.010316
Cor/Raça=Branca                                                                                               0.010064
dtype: float64
```
![image](https://github.com/user-attachments/assets/d961aa11-bab1-402c-ace4-7ff416af7935)
### Visualização do gráfico de importância da pior árvore
Entretanto, aqui a visualização dos atributos mais importantes deu mais ênfase em aspectos demográficos do que a atitude do profissional em caso da empresa adotar 100% presencial e o modelo de trabalho atual
```python
worst_importance = forest.estimators_[worst_tree].feature_importances_

worst_importance_series = pd.Series(worst_importance, index=vect.get_feature_names_out())
worst_importance_series = worst_importance_series.sort_values(ascending=False).head(10)

print(f'\nImportância das variáveis: \n{worst_importance_series}')

plt.figure(figsize=(5, 5))
worst_importance_series.plot(kind='barh', legend=False)
plt.title('Importância das variáveis (Pior árvore)')
plt.gca().invert_yaxis()
```
```
Importância das variáveis: 
Decisão da empresa para modelo 100% presencial=Vou aceitar e retornar ao modelo 100% presencial    0.352205
Forma de trabalho atual=Modelo 100% remoto                                                         0.093790
Região onde mora=Nordeste                                                                          0.044124
Faixa salarial=de R$ 6.001/mês a R$ 8.000/mês                                                      0.035272
Cargo atual=Analista de Dados/Data Analyst                                                         0.027648
Forma de trabalho atual=Modelo 100% presencial                                                     0.027511
Gênero=Masculino                                                                                   0.023162
Idade                                                                                              0.023008
Faixa salarial=de R$ 20.001/mês a R$ 25.000/mês                                                    0.022522
Nivel de segurança=Moderado                                                                        0.022458
```
![image](https://github.com/user-attachments/assets/06480712-f8e0-4364-8740-1adceb3c5b9a)
### Visualização do RandomForest
Uma vizualização de todas as 100 árvores com suas respectivas acurácias
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 5))
plt.plot(range(len(accuracies.items())), accuracies.values(), marker='o', linestyle='-', color='blue')
plt.title('Acurácia do Modelo Random Forest')
plt.xlabel('Número de Árvores')
plt.ylabel('Acurácia')
plt.ylim(0, 1)
plt.grid(True)
plt.show()
```
![image](https://github.com/user-attachments/assets/213544e1-4510-448b-8c87-ea7af2081315)
### Visualização da Árvore com melhor desempenho
```python
import pydotplus
from sklearn import tree
from IPython.display import Image

dot_data = tree.export_graphviz(forest.estimators_[best_tree], out_file=None, feature_names=vect.get_feature_names_out(), class_names=le.classes_, filled=True, rounded=True, special_characters=True)

graph = pydotplus.graph_from_dot_data(dot_data)
Image(graph.create_png())
```
![image](https://github.com/user-attachments/assets/96c40ac2-74c9-4699-8826-e9fada9535d8)
### Visualização da Árvore com pior desempenho
```python
import pydotplus
from sklearn import tree
from IPython.display import Image

dot_data = tree.export_graphviz(forest.estimators_[worst_tree], out_file=None, feature_names=vect.get_feature_names_out(), class_names=le.classes_, filled=True, rounded=True, special_characters=True)

graph = pydotplus.graph_from_dot_data(dot_data)
Image(graph.create_png())
```
![image](https://github.com/user-attachments/assets/575f77b2-a16a-48d2-8eb3-6eb5a5c4b6dc)
## Resultados

### Resultados obtidos com o modelo 1.

Análise da Matriz de Confusão
Resumo das Classes:

## Código das Classes

| Código | Classe                 |
|--------|------------------------|
| 0      | Modelo 100% presencial |
| 1      | Modelo 100% remoto     |
| 2      | Modelo híbrido         |

## Acurácia Geral

**Acurácia geral:** 74,6%  
O modelo acerta aproximadamente três quartos das classificações.

## Relatório de Classificação

| Classe | Precision | Recall | F1-Score | Suporte |
|--------|-----------|--------|----------|---------|
| 0      | 0.14      | 0.05   | 0.08     | 19      |
| 1      | 0.74      | 0.77   | 0.75     | 524     |
| 2      | 0.76      | 0.75   | 0.76     | 571     |

Análise da Matriz de Confusão:
Modelo 100% presencial (classe 0): Apenas 1 dos 19 exemplos foi corretamente classificado. A maioria foi confundida com o modelo híbrido (15 casos) e alguns com o modelo 100% remoto (3 casos). O desempenho é extremamente baixo devido ao severo desbalanceamento de classes.
Modelo 100% remoto (classe 1): 401 de 524 exemplos foram classificados corretamente. Houve 119 confusões com o híbrido, 4 com o presencial e nenhuma classificação incorreta significativa adicional. Apresenta desempenho satisfatório.
Modelo híbrido (classe 2): 429 de 571 exemplos foram classificados corretamente. Houve 140 confusões com o remoto, 2 com o presencial. Demonstra o melhor desempenho entre as três classes.

Matriz em forma de tabela:

| Classe Real \ Prevista | Modelo 100% presencial | Modelo 100% remoto | Modelo híbrido |
|------------------------|------------------------|--------------------|----------------|
| Modelo 100% presencial | 1                      | 3                  | 15             |
| Modelo 100% remoto     | 4                      | 401                | 119            |
| Modelo híbrido         | 2                      | 140                | 429            |

![image](https://github.com/user-attachments/assets/40653726-2954-4eae-9eb9-f171b6958a2e)

### Interpretação do Modelo 1

O Modelo 1 foi treinado para prever a forma de trabalho ideal entre três categorias: **modelo 100% presencial**, **modelo 100% remoto** e **modelo híbrido**. O algoritmo apresenta **acurácia de 74,6% no conjunto de teste** e **79,3% no treino**, o que sugere bom desempenho geral, mas com possíveis indícios de overfitting leve.

#### Métricas Gerais por Classe
- **"Modelo 100% remoto"**: melhor desempenho entre as classes (Precision: 0.74, Recall: 0.77, F1-Score: 0.75)
- **"Modelo híbrido"**: desempenho consistente (F1-Score: 0.76), com leve confusão com "remoto"
- **"Modelo 100% presencial"**: desempenho extremamente baixo (F1-Score: 0.08), com apenas 1 acerto em 19 exemplos

#### Padrões Observados
- A maior parte dos **erros ocorre entre as classes "remoto" e "híbrido"**, com 140 exemplos originalmente híbridos sendo classificados como remoto, e 119 exemplos remotos sendo classificados como híbrido.
- A classe **"100% presencial"** é praticamente ignorada pelo modelo, sendo confundida principalmente com o modelo híbrido (15 de 19 casos).
- O modelo apresenta **bom equilíbrio entre precisão e recall** nas classes mais numerosas (remoto e híbrido), mas falha com a classe minoritária (presencial).

#### Limitações Identificadas
- **Desbalanceamento de classes**: a baixa representatividade da classe "100% presencial" prejudica a capacidade do modelo de reconhecê-la.
- **Semelhança entre categorias híbrido e remoto**: os dados disponíveis não parecem capturar bem as diferenças conceituais entre essas duas formas de trabalho.
- A **macro média** das métricas (Precision: 0.55, Recall: 0.52, F1: 0.53) está abaixo do ideal, reforçando o impacto negativo da classe minoritária.


### Resultados obtidos com o modelo 2.

#### Análise da Matriz de Confusão do modelo 2

Melhor árvore

| Classe Real / Prevista | Modelo 100% presencial | Modelo 100% remoto | Modelo híbrido |
| ---------------------- | ---------------------- | ------------------ | -------------- |
| Modelo 100% presencial | 0                      | 1                  | 18             |
| Modelo 100% remoto     | 2                      | 356                | 166            |
| Modelo híbrido         | 1                      | 76                 | 494            |

![image](https://github.com/user-attachments/assets/7a692d74-e83f-41c1-87fd-4353d81c79f6)

Pior árvore

| Classe Real / Prevista | Modelo 100% presencial | Modelo 100% remoto | Modelo híbrido |
| ---------------------- | ---------------------- | ------------------ | -------------- |
| Modelo 100% presencial | 0                      | 1                  | 18             |
| Modelo 100% remoto     | 1                      | 290                | 233            |
| Modelo híbrido         | 4                      | 198                | 369            |

![image](https://github.com/user-attachments/assets/e6bd93ce-b71d-4b2b-a944-9ae2a6525fc6)

#### Análise Detalhada das Métricas por Classe

**Classe "Modelo híbrido"**

Melhor árvore:
Desempenho razoável com 59.6% de acertos (324/544). Os principais erros concentram-se em 36.7% dos casos classificados incorretamente como "Modelo 100% remoto" (200/544). A precisão é de 64.8% (324/500), indicando que, entre as previsões como "híbrido", a maioria estava correta.

Pior árvore:
Queda expressiva no desempenho, com recall de apenas 35.5% (193/544). A confusão com a classe "remoto" aumenta significativamente, com 60.8% dos casos (331/544) sendo erroneamente classificados como "Modelo 100% remoto". Isso evidencia alta sensibilidade do modelo a variações nos dados.

**Classe "Modelo 100% presencial"**

Melhor árvore:
Falha completa na identificação da classe, com 0% de acertos. A maioria dos casos (94.7% – 18/19) foi classificada incorretamente como "Modelo híbrido", e 5.3% como "Modelo 100% remoto".

Pior árvore:
Resultado ainda mais crítico: 100% dos casos (19/19) classificados como "Modelo híbrido". Isso reforça a completa negligência da classe minoritária, independentemente da configuração do modelo.

**Classe "Modelo 100% remoto"**

Melhor árvore:
Bom desempenho com 69.0% de acertos (394/571). Os principais erros se dão pela confusão com o "Modelo híbrido", responsável por 31.0% dos erros (177/571).

Pior árvore:
Queda relevante para 53.6% de acertos (306/571). A taxa de confusão com "Modelo híbrido" aumenta para 46.4% (265/571), demonstrando instabilidade no reconhecimento da classe.

#### Padrões Críticos Identificados
**Colapso da classe minoritária:**
A classe "Modelo 100% presencial" é completamente ignorada pelo modelo em ambas as árvores, sugerindo priorização excessiva das classes majoritárias em detrimento de representações críticas.

**Sobreposição entre Híbrido e Remoto:**
Confusões significativas entre "Modelo híbrido" e "Modelo 100% remoto" ocorrem em ambas as direções: 36.7% dos híbridos são confundidos com remoto, e 31.0% dos remotos com híbrido. Isso indica que as variáveis disponíveis não capturam adequadamente as distinções práticas entre os dois modelos.

**Instabilidade extrema:**
A variação de 24.1 pontos percentuais no recall da classe "Modelo híbrido" (de 59.6% para 35.5%) entre árvores sugere que o modelo é altamente sensível a pequenas variações nos dados de treinamento.

### Interpretação do modelo 2

O Modelo 2 utilizou random forest para prever a forma de trabalho ideal entre três categorias: **modelo 100% presencial**, **modelo 100% remoto** e **modelo híbrido**. A performance foi avaliada considerando a **melhor** e a **pior árvore** resultantes da Random Forest, a fim de identificar estabilidade e padrões de erro.

#### Métricas por Classe

- **"Modelo 100% remoto"**
  - Melhor árvore: 69,0% de acertos (Recall)
  - Pior árvore: Queda para 53,6%, com aumento da confusão para "modelo híbrido"
- **"Modelo híbrido"**
  - Melhor árvore: 59,6% de acertos; Precision: 64,8%
  - Pior árvore: Forte queda para 35,5% de acertos
- **"Modelo 100% presencial"**
  - Ambas as árvores: 0% de acerto; totalmente confundida com a classe "modelo híbrido"

#### Padrões Observados

- O modelo mostra **razoável capacidade de previsão** para as classes "remoto" e "híbrido", mas apresenta **forte instabilidade** entre execuções.
- A classe **"100% presencial"** é completamente ignorada pelo modelo, sendo sempre classificada como "híbrido". Isso evidencia um **colapso da classe minoritária**.
- Existe **sobreposição significativa** entre as classes "remoto" e "híbrido", com erros em ambas as direções:
  - 36,7% dos híbridos foram classificados como remoto
  - 31,0% dos remotos foram classificados como híbrido
- A variação no desempenho da classe híbrida entre melhor e pior árvore (**24,1 pontos percentuais de diferença no recall**) demonstra **alta sensibilidade do modelo aos dados de treino**.

#### Limitações Identificadas

- **Desbalanceamento de classes**: a classe "100% presencial" representa apenas 19 instâncias, o que contribui para sua não identificação.
- **Falta de variáveis discriminantes** entre híbrido e remoto: as features utilizadas parecem não capturar bem as diferenças conceituais entre os dois.
- **Instabilidade estrutural**: a Random Forest sofre variações expressivas entre árvores individuais, o que pode afetar a confiabilidade geral do modelo.

### Análise Comparativa dos Modelos

#### Modelo 1 — Árvore de Decisão Única
- **Acurácia no teste:** 74,6%
- **Pontos fortes:**
  - Simples de interpretar.
  - Desempenho sólido para as classes **remoto** e **híbrido**, com F1-scores em torno de 0.75 e 0.76.
- **Pontos fracos:**
  - Desempenho extremamente baixo para a classe **100% presencial** (F1-score: 0.08), com apenas 1 acerto em 19.
  - Confusões recorrentes entre **remoto** e **híbrido**, refletindo sobreposição entre as duas categorias.

#### Modelo 2 — Random Forest
- **Acurácia geral da melhor árvore:** não especificada, mas análise detalhada por classe disponível.
- **Pontos fortes:**
  - Melhor capacidade de generalização e robustez a ruído por ser um ensemble de árvores.
  - Desempenho semelhante ao Modelo 1 nas classes **remoto** e **híbrido**.
- **Pontos fracos:**
  - A classe **100% presencial** continuou com 0% de acerto em todas as árvores.
  - Alta **instabilidade** nas previsões da classe híbrida: o recall caiu de 59,6% para 35,5% entre a melhor e pior árvore.
  - Confusão significativa entre **remoto** e **híbrido** persistiu, com até 60,8% dos híbridos sendo classificados como remotos.

#### Comparação Direta

| Critério                        | Modelo 1 (Árvore Única) | Modelo 2 (Random Forest) |
|--------------------------------|--------------------------|---------------------------|
| Facilidade de interpretação    | Alta                     | Baixa/moderada            |
| Robustez e estabilidade        | Baixa                    | Moderada (mas instável)   |
| Desempenho geral               | Bom                      | Bom (mas com variação)    |
| Classe "Remoto"                | Ótimo                    | Ótimo a razoável          |
| Classe "Híbrido"               | Ótimo                    | Variável (dependendo da árvore) |
| Classe "Presencial"           | Ruim (quase ignorada)    | Ruim (completamente ignorada) |

#### Quando um modelo se sairia melhor?

- **Modelo 1 (Árvore Única)** é mais adequado quando:
  - A interpretação do processo de decisão é importante (por exemplo, explicar previsões a gestores).
  - O contexto exige um modelo leve, rápido de treinar e aplicar.

- **Modelo 2 (Random Forest)** se sairia melhor quando:
  - O objetivo é maior **robustez geral**, mesmo com alguma perda de interpretabilidade.
  - Há necessidade de lidar com variações nos dados de entrada.
  - Deseja-se mitigar o risco de overfitting de uma única árvore, apesar da instabilidade observada.

**Conclusão**

Ambos os modelos apresentaram bom desempenho na previsão das classes "modelo 100% remoto" e "modelo híbrido", ainda que com confusões recorrentes entre essas duas categorias, possivelmente pela proximidade conceitual. A Árvore de Decisão (Modelo 1) se destaca pela simplicidade e facilidade de interpretação, enquanto a Random Forest (Modelo 2) oferece maior robustez, mas com variações mais sensíveis entre execuções.
A escolha entre os modelos depende do objetivo: o Modelo 1 é preferível quando a transparência do processo decisório é essencial, enquanto o Modelo 2 pode ser mais indicado quando se busca maior capacidade de generalização, desde que se tome cuidado com a instabilidade observada.

## 8. Conclusão

O trabalho buscou identificar quais fatores mais influenciam na escolha do modelo de trabalho entre profissionais da área de Dados.

**Márcio Douglas Cassemiro Junior**

Os modelos utilizados, como Decision Tree e Random Forest, apresentaram desempenhos semelhantes. Ambos tiveram dificuldades em prever corretamente os casos do modelo presencial, principalmente devido à baixa quantidade de registros dessa categoria na base de dados. Por outro lado, os modelos obtiveram bons resultados na classificação dos modelos remoto e híbrido, embora tenha havido certa confusão entre essas duas classes — confusão que, até o momento, não consegui identificar com clareza.

Em relação às bases auxiliares utilizadas, percebi que os modelos atribuíram pouca importância a elas. Acredito que dados mais específicos e concretos sobre os trabalhadores poderiam ajudar a melhorar a acurácia dos modelos, como por exemplo: tipo de transporte utilizado para ir ao trabalho, tempo médio de deslocamento, presença de filhos, gastos mensais, entre outros. No entanto, por se tratarem de informações pessoais, não foi possível obtê-los para esta pesquisa.

Além disso, seria importante também incluir mais registros de pessoas que preferem o modelo presencial, o que poderia ajudar a reduzir a confusão entre as classes e melhorar o desempenho geral do modelo.

Apesar das limitações e possíveis erros, acredito que os modelos desenvolvidos são sim capazes de identificar o modelo de trabalho mais adequado para profissionais da área de Dados, especialmente considerando que a maioria demonstrou preferência pelos modelos remoto e híbrido.

**Gustavo Vasconcellos Horta**

Apesar dos desafios enfrentados no início, a análise foi ganhando corpo à medida que nos aprofundamos nas bases de dados e compreendemos melhor a lógica por trás dos resultados. A princípio, interpretar as informações e cruzá-las de forma significativa não foi tarefa simples — especialmente na hora de relacionar variáveis e entender como cada uma influenciava na categorização dos regimes de trabalho.

A matriz de confusão, por exemplo, se mostrou uma ferramenta central nesse processo. No começo, parecia apenas um conjunto de números difíceis de interpretar. Mas, com o tempo, ela se revelou essencial para entender onde os modelos estavam acertando e, principalmente, onde estavam errando. Foi por meio dela que identificamos a dificuldade persistente dos algoritmos em distinguir entre os regimes remoto e híbrido. A sobreposição entre essas duas categorias, evidenciada pelos falsos positivos e negativos, levantou questionamentos importantes sobre os limites dos dados disponíveis.

A exploração das bases complementares também teve um papel relevante, ainda que seus impactos tenham sido mais discretos do que esperávamos. A expectativa era que elas trouxessem nuances novas à análise, mas, ao fim, percebeu-se que sua contribuição foi limitada. Provavelmente, a ausência de variáveis mais contextuais — como tempo de deslocamento, rotina familiar ou mesmo custos relacionados ao trabalho — acabou restringindo o poder preditivo dos modelos. Entendemos que, por envolverem informações pessoais, esses dados são mais difíceis de obter, mas sua inclusão poderia fazer uma grande diferença.

Apesar das limitações, a experiência como um todo foi bastante enriquecedora. Com o grupo trabalhando em conjunto, fomos aprendendo a ajustar as rotas à medida que os obstáculos surgiam. A compreensão da matriz de confusão, a reinterpretação das variáveis e a forma como exploramos as bases foram se aperfeiçoando ao longo do processo.

Se um dia houver a chance de refinar ainda mais esse estudo, gostaria de testar a inclusão de novas variáveis mais qualitativas e, especialmente, reequilibrar melhor a amostra — com atenção especial ao regime presencial, que hoje ainda aparece de forma tímida na base.

**Luiz Felipe Assis Cavalcante**

Neste trabalho, desenvolvemos dois modelos preditivos: uma Árvore de Decisão e uma Random Forest. Ambos foram construídos para responder à pergunta orientada a dados: quais fatores influenciam na forma de trabalho ideal dos profissionais da área de ciência de dados. Inicialmente, a tentativa foi prever quatro categorias: híbrido fixo, híbrido flexível, remoto e presencial. No entanto, para melhorar a performance dos modelos, optamos por agrupar os dois tipos de modelo híbrido em uma única categoria, resultando nas classes: híbrido, remoto e presencial.

Durante a análise dos resultados, observamos que ambos os modelos apresentaram desempenho razoável, com acurácia em torno de 70%. As previsões para as classes "remoto" e "híbrido" foram satisfatórias. No entanto, houve falha na identificação correta da classe "presencial", o que acredito estar relacionado ao número reduzido de registros dessa categoria na base de dados. Essa limitação compromete os resultados, considerando que a distinção entre presencial e outras formas de trabalho é essencial para o objetivo da análise. Além disso, enfrentamos dificuldades para encontrar bases de dados válidas que se relacionassem diretamente com o tema e, principalmente, que pudessem ser cruzadas com a base principal "State of Data", que era obrigatória no projeto.

Concluo que, se tivesse a oportunidade de refazer o projeto, escolheria com mais cuidado a pergunta orientada a dados, levando em consideração a disponibilidade, qualidade e compatibilidade das bases de dados desde o início. Isso permitiria estruturar uma solução mais consistente e representativa, com melhores condições para interpretar os resultados obtidos.

...

# REFERÊNCIAS

**[1]** IBGE – Instituto Brasileiro de Geografia e Estatística.
Roubos e furtos por região. Tabela 8756. Disponível em: https://sidra.ibge.gov.br/tabela/8756.

**[2]** IBGE – Instituto Brasileiro de Geografia e Estatística.
Média de horas de trabalho doméstico e tarefas de cuidado. Tabela 9379. Disponível em: https://sidra.ibge.gov.br/tabela/9379.

**[3]** OPENAI.
ChatGPT. Disponível em: https://chatgpt.com/.

**[4]** PERPLEXITY AI.
Perplexity. Disponível em: https://www.perplexity.ai/.

**[5]** DATA HACKERS.
State of Data 2023 – Brasil. Kaggle, 2023. Disponível em: https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-2023.

**[6]** GOOGLE.
Google Colab. Disponível em: https://colab.google/.

**[7]** SCIKIT-LEARN.
Random Forest – sklearn.ensemble.RandomForestClassifier. Disponível em: https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html.

**[8]** SCIKIT-LEARN.
Decision Tree – sklearn.tree. Disponível em: https://scikit-learn.org/stable/modules/tree.html.

**[9]** PUC MINAS – Pontifícia Universidade Católica de Minas Gerais.
Arquivos de modelos. Disponível em: https://pucminas.instructure.com/courses/226410/files.

# APÊNDICES

**Colocar link:**

Do código (armazenado no repositório);

Dos artefatos (armazenado do repositório);

Da apresentação final (armazenado no repositório);

Do vídeo de apresentação (armazenado no repositório).
