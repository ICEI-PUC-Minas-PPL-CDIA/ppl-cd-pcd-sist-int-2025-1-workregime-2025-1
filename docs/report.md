# Regime de Trabalho na Área de Dados: Preferências Entre Remoto, Híbrido e Presencial


**Luiz Felipe Assis Cavalcante, lfacavalcante@sga.pucminas.br**

**João Vitor de Lima, joao.lima.1594303@sga.pucminas.br**

**Márcio Douglas Cassemiro Junior, marcio.cassemiro@sga.pucminas.br**

**Gustavo Horta, gustavo.horta.1524459@sga.pucminas.br**


---

Professores:

**Prof. Hugo de Paula**</br>
**Prof. Hayala Curto** 

---

_Curso de Ciência de Dados, Unidade Praça da Liberdade_

_Instituto de Informática e Ciências Exatas – Pontifícia Universidade de Minas Gerais (PUC MINAS), Belo Horizonte – MG – Brasil_

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

###    Objetivo geral

Desenvolver um sistema inteligente capaz de identificar padrões na escolha do regime de trabalho (remoto, híbrido ou presencial) e analisar os principais fatores que influenciam essa decisão. O sistema levará em consideração aspectos como mobilidade urbana, cargo, preferências dos profissionais e outras variáveis relevantes, gerando insights para empresas e formuladores de políticas trabalhistas.

####    Objetivos específicos

- Identificar os principais fatores que influenciam a escolha dos profissionais de dados pelo regime de trabalho remoto, híbrido ou presencial.  
- Analisar a variação das preferências por regime de trabalho de acordo com cargo, setor de atuação e localização.  
- Comparar os impactos da interação social e do tempo de deslocamento na decisão pelo modelo de trabalho adotado.  

###    Justificativas

Este estudo se justifica pela necessidade de fornecer uma base analítica que auxilie empresas na formulação de cargos e na escolha do regime de trabalho mais adequado, considerando o perfil dos profissionais que possuem ou desejam atrair. Ao identificar os fatores que influenciam essa decisão, a pesquisa permite que organizações alinhem suas estratégias às expectativas do mercado, reduzindo a rotatividade e aumentando o engajamento dos colaboradores.

Além disso, compreender a relação entre fatores como cargo, setor de atuação, tempo de deslocamento e interação social pode ajudar empresas a ajustar suas políticas de trabalho para atender melhor às necessidades dos profissionais. Dessa forma, a pesquisa contribui para a construção de ambientes mais flexíveis e alinhados às novas dinâmicas do mercado pós-pandemia, beneficiando tanto as empresas quanto os trabalhadores.

##    Público alvo

O público-alvo desse sistema inclui empresas de diversos setores que desejam entender melhor as preferências de seus funcionários em relação ao regime de trabalho, auxiliando na formulação de políticas mais eficientes e atrativas. Além disso, gestores de Recursos Humanos podem utilizá-lo para otimizar modelos de trabalho e retenção de talentos. Pesquisadores e formuladores de políticas públicas também podem se beneficiar dos dados gerados para analisar impactos na mobilidade urbana, produtividade e qualidade de vida dos trabalhadores. Startups e consultorias especializadas em transformação digital e cultura organizacional podem usar os insights do sistema para oferecer soluções personalizadas a seus clientes.

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

### Modelo 1: Árvore de decisão
Optamos por utilizar o algoritmo Decision Tree como parte da nossa análise por se tratar de um modelo intuitivo, interpretável e eficaz em tarefas de classificação, especialmente quando se lida com variáveis categóricas e numéricas. Como nosso objetivo é compreender os fatores que influenciam a escolha do regime de trabalho (presencial, híbrido ou remoto), a Decision Tree se mostrou uma escolha valiosa por sua capacidade de representar decisões de forma hierárquica, facilitando a visualização lógica do processo de classificação.

Além disso, esse modelo permite observar quais atributos são priorizados nas decisões ao longo dos ramos da árvore, o que contribui diretamente para a interpretação dos resultados. Embora a Decision Tree possa estar mais sujeita a overfitting em comparação com algoritmos mais complexos, sua simplicidade e transparência tornam-na ideal para análises exploratórias e didáticas, especialmente quando se busca compreender a influência de variáveis específicas em uma decisão. Dessa forma, ela complementa o uso de modelos mais robustos, como o Random Forest, oferecendo uma visão clara e estruturada dos critérios adotados pelo algoritmo.
#### Transformando os dados
Nesta etapa, devido à presença de muitas variáveis categóricas no dataset, foi necessário convertê-las para o formato numérico, tornando-as adequadas para o treinamento do modelo de Árvore de decisão. Algumas colunas foram removidas antes da transformação, pois serviram como base para a criação de uma nova variável. Especificamente, utilizamos a soma total de roubos registrados para gerar uma nova coluna chamada "Nível de Segurança", que classifica os dados em três categorias: baixo, moderado e alto. Essa classificação foi realizada com o auxílio da função `qcut` do pandas, que divide os valores em faixas com base em quantis.

Além das colunas utilizadas na criação do "Nível de Segurança", também foi removida a coluna TARGET, que representa a variável "forma de trabalho ideal", por se tratar da variável a ser prevista.

Após a exclusão dessas colunas, os dados categóricos restantes foram transformados em dados numéricos com o uso do `DictVectorizer`, ferramenta que converte dicionários de variáveis categóricas em arrays numéricos, mantendo a estrutura necessária para o modelo de machine learning.
```python
# Separar variáveis independentes e alvo
X_dict = df.drop(columns=['Roubos de veículo', 'Roubos de carro', 'Roubos de moto', 'Roubos de bicicleta', 'Roubos fora do domicílio', 'Total de roubos', 'Forma de trabalho ideal']).to_dict(orient='records')
vect = DictVectorizer(sparse=False)
X = vect.fit_transform(X_dict)
```
Após a transformação das variáveis categóricas, também foi realizada a codificação da variável alvo utilizando o `LabelEncoder`, que converte os rótulos em valores numéricos, tornando-os compatíveis com o modelo de machine learning.
```python
le = LabelEncoder()
y = le.fit_transform(df['Forma de trabalho ideal'])
```
Em seguida, os dados foram divididos em conjuntos de treino e teste utilizando a função `train_test_split`, com **80% dos dados destinados ao treinamento** e **20% ao teste**. Essa proporção foi escolhida com base em experimentos realizados ao longo do desenvolvimento, nos quais essa configuração apresentou os melhores resultados em termos de acurácia.
```python
# Dividir os dados corretamente
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
#### Indução do Modelo
Na etapa de treinamento, o primeiro passo foi a criação do modelo `DecisionTreeClassifier` com parâmetros definidos. Adotamos o critério de entropia para a divisão dos nós. A entropia mede o grau de impureza das amostras em um nó, buscando maximizar o ganho de informação a cada divisão. Apesar de as classes no nosso conjunto de dados estarem desbalanceadas, optamos pela entropia por sua maior sensibilidade na separação de classes minoritárias, o que é relevante para nosso objetivo de compreender os fatores que influenciam todas as formas de trabalho — inclusive aquelas com menor representação.

Além disso, definimos uma profundidade máxima de árvore (`max_depth=5`) para evitar overfitting. Testamos também os valores maiores que 5, mas observamos que profundidades maiores aumentaram a complexidade do modelo e reduziram o desempenho na base de teste. O valor 5 apresentou o melhor equilíbrio entre acurácia e generalização.
```python
# Definir modelo com limitação de profundidade e folhas mínimas
treeForma = DecisionTreeClassifier(random_state=42, criterion='entropy', max_depth=5)
treeForma.fit(X_train, y_train)
print("Acurácia no treino:", treeForma.score(X_train, y_train))
```
Após o treinamento do modelo, realizamos a etapa de teste utilizando o método `predict` nos dados reservados para validação. O modelo obteve uma acurácia de **78% em ambos os casos**, com pequenas diferenças, indicando um bom desempenho geral e uma razoável capacidade de generalização. No entanto, embora esses resultados sejam promissores, a análise da matriz de confusão, que será detalhada mais adiante nesta documentação, revela limitações importantes relacionadas à forma como o modelo trata classes menos representadas. Ainda assim, os resultados oferecem uma base relevante e orientada por dados para responder à nossa pergunta de pesquisa, especialmente no que se refere às tendências predominantes.
```python
# Avaliação no conjunto de teste
y_pred = treeForma.predict(X_test)
print("Acurácia no teste:", accuracy_score(y_test, y_pred))
```
```
Acurácia no treino: 0.7890583903208838
Acurácia no teste: 0.7812828601472135
```
##### Outros valores testados
*test_size=0.2 & max_depth=7*
```
Acurácia no treino: 0.8037874802735402
Acurácia no teste: 0.7539432176656151
```
*test_size=0.2 & max_depth=9*
```
Acurácia no treino: 0.8271962125197264
Acurácia no teste: 0.7371188222923238
```
*test_size=0.3 & max_depth=5*
```
Acurácia no treino: 0.7868951006913135
Acurácia no teste: 0.7678821879382889
```
*test_size=0.3 & max_depth=7*
```
Acurácia no treino: 0.7956116621581004
Acurácia no teste: 0.7433380084151473
```
#### Exibição da Árvore de Decisão
Como o modelo utilizado nesta etapa é uma árvore de decisão única (por meio do `DecisionTreeClassifie`), é possível visualizar toda a sua estrutura de forma clara e completa. Essa visualização permite compreender exatamente como o modelo realiza as divisões nos dados, seguindo critérios baseados nos atributos mais relevantes para a tarefa de classificação.

Para gerar essa representação gráfica, utilizamos a função `export_graphviz` da biblioteca `sklearn.tree`, que converte a estrutura da árvore em um código no formato DOT — uma linguagem voltada para a descrição de grafos. Esse código é processado pela biblioteca `pydotplus`, que o transforma em um gráfico visual. Por fim, a imagem é exibida com `IPython.display.Image`, mostrando os nós da árvore com os atributos de decisão, valores de corte, classes previstas e cores que indicam a predominância de cada classe em cada subdivisão.

Essa abordagem facilita a interpretação dos critérios adotados pelo modelo e oferece uma visão transparente e intuitiva sobre o processo de classificação, tornando o funcionamento interno do algoritmo mais acessível e compreensível mesmo para públicos não técnicos.
```python
import pydotplus
from sklearn import tree
from IPython.display import Image

dot_data = tree.export_graphviz(treeForma, out_file=None, feature_names=vect.get_feature_names_out(), class_names=le.classes_, filled=True, rounded=True, special_characters=True)

graph = pydotplus.graph_from_dot_data(dot_data)
Image(graph.create_png())
```
![image](https://github.com/user-attachments/assets/66f9ee69-cf36-4b53-987d-da9514905be0)
### Modelo 2: Random Forest
Para o segundo modelo, optamos por utilizar o Random Forest, que, diferentemente do DecisionTreeClassifier, não se baseia em uma única árvore de decisão, mas sim em um conjunto (ou "floresta") de múltiplas árvores. Enquanto o DecisionTreeClassifier constrói uma única árvore que aprende diretamente com os dados e pode sofrer com overfitting, o Random Forest cria várias árvores de decisão independentes e combina os resultados de todas elas para tomar uma decisão final (geralmente por votação, no caso de classificação). Essa abordagem reduz a variância do modelo, melhora a capacidade de generalização e tende a oferecer resultados mais robustos, especialmente em conjuntos de dados mais complexos ou com ruído.

Os códigos apresentados a seguir seguem a mesma lógica já aplicada ao modelo `DecisionTreeClassifier`. Por esse motivo, a explicação será mais concisa, uma vez que os procedimentos e conceitos envolvidos são semelhantes aos utilizados anteriormente, sendo adaptados apenas ao uso do modelo `RandomForestClassifier`.

#### Gerando base de treinamento e teste
Nesta etapa, foram removidas as colunas que não são relevantes para o treinamento do modelo, incluindo o atributo alvo. Em seguida, utilizando o `DictVectorizer` foi feita a conversão dos dados categóricos restantes para valores numéricos, permitindo que fossem utilizados adequadamente no processo de modelagem.
```python
X_dict = data.drop(columns=['Roubos de veículo', 'Roubos de carro', 'Roubos de moto', 'Roubos de bicicleta', 'Roubos fora do domicílio', 'Total de roubos', 'Forma de trabalho ideal'], axis=1).T.to_dict().values()
vect = DictVectorizer(sparse=False)
X = vect.fit_transform(X_dict)
```
Nesta etapa, o atributo alvo foi convertido para valores numéricos utilizando o `LabelEncoder`, permitindo que o modelo de machine learning possa interpretá-lo corretamente durante o treinamento e a avaliação.
```python
le = LabelEncoder()
y = le.fit_transform(data.iloc[:, data.shape[1]-1])
```
Em seguida, os dados foram divididos em 80% para treinamento e 20% para teste, seguindo a mesma lógica adotada no primeiro modelo. Essa padronização na divisão permite uma comparação justa e consistente entre os resultados obtidos por ambos os algoritmos.
```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
#### Treinando o Random Forest
Na etapa de treinamento, seguimos a mesma lógica aplicada ao primeiro modelo, realizando apenas ajustes nos parâmetros específicos do `RandomForestClassifier`. O parâmetro `n_estimators` (número de árvores) foi mantido em 100, valor padrão do algoritmo. Optamos novamente pelo critério de entropia, considerando que nossos dados estão desbalanceados, e buscamos manter a coerência com o modelo anterior. O parâmetro `max_depth` foi definido como `5`. Embora esse valor tenha apresentado um desempenho inferior ao `max_depth=8` em testes com a Random Forest, decidimos mantê-lo para garantir uma base de comparação justa entre os modelos e, assim, avaliar qual abordagem se mostrou mais eficaz para responder à nossa pergunta orientada a dados.
```python
forest = RandomForestClassifier(n_estimators=100, random_state=42, criterion='entropy', max_depth=5)
forest.fit(X_train, y_train)
print(f'Acurácia do treinamento: {forest.score(X_train, y_train)}')
```
Após o treinamento do modelo, realizamos a etapa de predição utilizando os dados de teste. Diferentemente do `DecisionTreeClassifier`, o modelo de Random Forest apresentou um desempenho ligeiramente inferior nos dados de teste, alcançando **78% de acurácia no treinamento** e **76% nos dados de teste**. Apesar dessa leve queda, consideramos que o modelo ainda demonstra uma boa capacidade de aprendizado e generalização. Levando em conta suas limitações e a natureza dos dados, especialmente o desbalanceamento entre as classes, o Random Forest ainda se mostra capaz de oferecer respostas coerentes e relevantes dentro do escopo da nossa análise orientada a dados.
```python
y_pred = forest.predict(X_test)
print(f'Acurácia do teste: {accuracy_score(y_test, y_pred)}')
```
```
Acurácia do treinamento: 0.7856391372961599
Acurácia do teste: 0.7613038906414301
```
##### Outros valores testados
*test_size=0.2, max_depth=8*
```
Acurácia do treinamento: 0.8264071541294056
Acurácia do teste: 0.7844374342797056
```
*test_size=0.3, max_depth=5*
```
Acurácia do treinamento: 0.7956116621581004
Acurácia do teste: 0.7636746143057503
```
*test_size=0.3, max_depth=8*
```
Acurácia do treinamento: 0.8358881875563571
Acurácia do teste: 0.7622720897615708
```
#### Visualização de uma Árvore
Como uma Random Forest é composta por dezenas ou até centenas de árvores de decisão — neste caso, 100 — não é viável exibir todas elas em uma única visualização, pois isso tornaria a análise extremamente complexa e pouco informativa. Para fins didáticos e de interpretação, optamos por exibir apenas a primeira árvore gerada pelo modelo. Essa abordagem permite visualizar de forma clara e simplificada como o algoritmo realiza as divisões de decisão, oferecendo uma amostra representativa da lógica usada pela floresta para realizar previsões, sem comprometer a legibilidade.

Para essa visualização, utilizamos o mesmo código aplicado anteriormente na exibição da árvore de decisão, realizando apenas uma pequena modificação: utilizamos forest.estimators_[0] para selecionar a primeira árvore da floresta do modelo Random Forest. Essa abordagem permite visualizar detalhadamente como uma das árvores individuais do conjunto realiza suas divisões, facilitando a compreensão do funcionamento interno do modelo.
```python
import pydotplus
from sklearn import tree
from IPython.display import Image

dot_data = tree.export_graphviz(forest.estimators_[0], out_file=None, feature_names=vect.get_feature_names_out(), class_names=le.classes_, filled=True, rounded=True, special_characters=True)

graph = pydotplus.graph_from_dot_data(dot_data)
Image(graph.create_png())
```
![image](https://github.com/user-attachments/assets/b2bbafe8-94e8-429d-bd7d-303dc114aeda)
## Resultados

### Resultados obtidos com o modelo 1.

#### Resultados com Classification Report
Nesta etapa, foi incluída uma tabela com o `classification_report`, que fornece métricas detalhadas de desempenho para cada classe do atributo alvo. Esse relatório apresenta valores de **precisão (precision)**, **revocação (recall)**, **f1-score** e **suporte (support)**, permitindo uma análise mais aprofundada de como o modelo está se comportando individualmente em relação a cada classe — especialmente útil para avaliar o impacto do desbalanceamento entre elas.
```python
print(classification_report(y_test, y_pred))
```
```
              precision    recall  f1-score   support

           0       0.00      0.00      0.00        21
           1       0.82      0.70      0.75       416
           2       0.76      0.88      0.81       514

    accuracy                           0.78       951
   macro avg       0.53      0.53      0.52       951
weighted avg       0.77      0.78      0.77       951
```

Ao observar o relatório de classificação do modelo treinado fica evidente que há um desempenho bastante desigual entre as classes. A classe 0, que representa o regime presencial, apresentou precision, recall e f1-score igual a 0.00. Isso indica que o modelo não conseguiu identificar corretamente nenhum exemplo real dessa classe no conjunto de teste, o que revela uma séria limitação em lidar com classes minoritárias.

Por outro lado, o modelo teve desempenho mais robusto nas classes mais representadas nos dados. A classe 1 (remoto) alcançou 82% de precisão, ou seja, a maior parte das previsões feitas para essa classe estavam corretas. No entanto, o recall foi de 70%, o que indica que 30% dos exemplos realmente remotos foram classificados como outra classe, principalmente como híbrido. Já a classe 2 (híbrido) teve o melhor desempenho, com recall de 88% e precisão de 76%, demonstrando que o modelo identificou corretamente a maioria dos exemplos dessa classe, embora ainda com alguma confusão.

A acurácia geral do modelo foi de 78%, o que à primeira vista pode parecer um bom resultado. No entanto, esse valor é enganoso, pois reflete principalmente o desempenho sobre as classes majoritárias. As métricas de macro average (média simples entre as classes) ficaram por volta de 0.53, um valor significativamente mais baixo, evidenciando que o modelo falhou em dar atenção equilibrada às três classes. Já as weighted averages (média ponderada pelo número de amostras) ficaram em torno de 0.77-0.78, puxadas para cima pelas classes mais frequentes.

#### Desenvolvimento da Matriz de confusão
No trecho de código abaixo, a matriz de confusão foi gerada com base nos dados de teste do modelo, utilizando três abordagens: primeiro, a matriz foi exibida em sua forma crua (valores numéricos); em seguida, foi formatada com os nomes das classes da variável alvo para facilitar a interpretação; por fim, utilizamos a função `ConfusionMatrixDisplay` para apresentar a matriz de forma visual, por meio de um gráfico que torna mais intuitiva a identificação dos acertos e erros do modelo.
```python
cnf_matrix = confusion_matrix(y_test, y_pred)
print(cnf_matrix)
```
```
[[  0   3  18]
 [  0 292 124]
 [  0  63 451]]
```
```python
cnf_table = pd.DataFrame(cnf_matrix, index=[f"Real={c}" for c in le.classes_], columns=[f"Prev={c}" for c in le.classes_])
print(cnf_table)
```
```
                            Prev=Modelo 100% presencial  Prev=Modelo 100% remoto Prev=Modelo híbrido
Real=Modelo 100% presencial                           0   		       3		  18
Real=Modelo 100% remoto                               0   		     292		 124
Real=Modelo híbrido                                   0   		      63		 451
```
```python
display = ConfusionMatrixDisplay.from_estimator(treeForma, X_test, y_test, display_labels=le.classes_, cmap=plt.cm.Blues)

plt.xticks(rotation=90)
plt.show()
```
![image](https://github.com/user-attachments/assets/fdd226ca-ed07-43f1-9006-57fec69149e1)

**Análise da Matriz de Confusão**

A análise da matriz de confusão revela um padrão claro de desempenho desigual do modelo em relação às diferentes classes do atributo alvo — particularmente no que diz respeito à classe “Modelo 100% presencial”. Conforme os dados apresentados, o modelo não foi capaz de classificar corretamente nenhum exemplo dessa categoria: dos 21 exemplos reais, 3 foram classificados como “Modelo 100% remoto” e 18 como “Modelo híbrido”, resultando em um total de 0 previsões corretas para essa classe. Isso se reflete diretamente nas métricas do classification report, com precisão, revocação e f1-score todos igual a 0.00 para a classe 0, um forte indicativo de que o modelo falha completamente ao lidar com essa categoria minoritária.

Já a classe “Modelo 100% remoto” (classe 1) apresenta um desempenho moderado: dos 416 exemplos reais, 292 foram corretamente classificados, mas ainda assim 124 foram erroneamente atribuídos como “Modelo híbrido”. O modelo demonstra boa precisão (82%) para essa classe, ou seja, quando ele prevê “remoto”, geralmente está correto. Contudo, o recall de 70% mostra que há uma taxa considerável de perda de exemplos reais dessa classe, o que compromete a cobertura.

A classe “Modelo híbrido” (classe 2) é a que o modelo lida melhor. Dos 514 exemplos reais, 451 foram corretamente classificados, resultando em uma taxa de recall alta (88%). Apesar de 63 exemplos terem sido classificados incorretamente como “remoto”, a precisão ainda se mantém em um nível razoável (76%). Esses números sugerem que o modelo está tendendo a classificar dados como “híbrido” com frequência, o que pode indicar um viés favorecendo a classe mais numerosa, comum em situações de desbalanceamento.

A acurácia geral do modelo, de 78%, pode inicialmente parecer satisfatória. No entanto, a análise da matriz de confusão em conjunto com as métricas do classification report revela que essa acurácia está inflada pelo bom desempenho nas classes com maior número de amostras (remoto e híbrido), mascarando a ineficácia completa na detecção da classe “presencial”. As médias macro (simples) — com valores por volta de 0.53 para precisão, recall e f1-score — apontam para uma performance fraca quando todas as classes são consideradas igualmente. Já as médias ponderadas (weighted avg) são mais altas, refletindo o domínio das classes majoritárias.

Conclui-se, portanto, que o modelo atual não é adequado para tarefas em que a correta identificação da classe “Modelo 100% presencial” seja crítica. A ausência total de previsões corretas para essa classe indica que o modelo precisa ser ajustado — seja por meio de técnicas de balanceamento de classes, ajuste de pesos ou melhoria da representação dos dados — para garantir um desempenho mais justo e confiável entre todas as categorias.

#### Exibição da Importância dos Atributos
No código a seguir, utilizamos o atributo `feature_importances_` do modelo `DecisionTreeClassifier` para visualizar quais variáveis tiveram maior influência na previsão da variável alvo. Para isso, os valores de importância foram organizados em um objeto `pd.Series`, que é uma estrutura de dados unidimensional do pandas, semelhante a uma lista rotulada, onde cada valor está associado a um índice — neste caso, os nomes das variáveis do conjunto de dados. Em seguida, criamos um gráfico de barras utilizando a biblioteca matplotlib, com o objetivo de facilitar a interpretação visual das importâncias atribuídas a cada atributo pelo modelo.
```python
# Exibir importâncias dos atributos
importances = pd.Series(treeForma.feature_importances_, index=vect.feature_names_)
importances = importances[importances > 0].sort_values(ascending=False).head(10)

# Gerando o gráfico
importances.plot(kind='barh', figsize=(10, 6), title='Importância dos Atributos')
plt.gca().invert_yaxis()
plt.show()
```
![image](https://github.com/user-attachments/assets/079d0305-65c0-4295-b793-497df11f8c53)

O gráfico de importância dos atributos mostra que o modelo de Decision Tree baseava suas decisões fortemente em uma única variável: **“Decisão da empresa para modelo 100% presencial = Vou procurar outra oportunidade no modelo 100% remoto”**, que sozinha responde por mais de 65% da importância atribuída às variáveis do modelo. Isso indica um viés muito forte do modelo em relação a essa informação específica.

A segunda variável mais relevante foi **“Forma de trabalho atual = Modelo 100% remoto”**, mas com uma importância significativamente menor (por volta de 20%). As demais variáveis — como idade, situação contratual, cargo atual, condição de PCD e estado de residência — praticamente não tiveram impacto na construção da árvore, com valores de importância muito baixos.

Esse comportamento sugere que o modelo, sem o balanceamento dos dados, encontrou padrões muito específicos ligados à preferência ou ao histórico de trabalho remoto, e se apoiou quase exclusivamente neles para classificar os dados. Como consequência, ele tende a ignorar outros aspectos relevantes, o que ajuda a explicar o mau desempenho na classificação da classe minoritária (trabalho 100% presencial), como também evidenciado pela matriz de confusão.

#### Visualização com SHAP
No trecho de código a seguir, aplicamos a biblioteca SHAP para interpretar o modelo de Árvore de decisão e entender a influência de cada variável nas previsões de forma mais transparente. Primeiramente, utilizamos o `LabelEncoder` previamente ajustado para recuperar os nomes reais das classes da variável alvo, armazenando-os na variável `class_names`.

Em seguida, criamos um objeto explainer a partir de `shap.TreeExplainer(treeForma)`, que é uma ferramenta otimizada para interpretar modelos baseados em árvores de decisão, como o `DecisionTreeClassifier`. Com o explainer, calculamos os valores de SHAP para os dados de teste (`X_test`) por meio da função `shap_values = explainer.shap_values(X_test)`. Esses valores representam, para cada amostra, quanto cada variável contribuiu positiva ou negativamente para a previsão de cada classe.

Por fim, o gráfico gerado com `shap.summary_plot()` apresenta uma visualização em barras `(plot_type='bar')` das variáveis mais importantes para o modelo. O parâmetro `feature_names` insere os nomes originais das variáveis, obtidos do `DictVectorizer`, e o argumento `class_names=class_names` substitui os rótulos genéricos como “Class 0” por nomes reais, tornando a visualização mais legível e interpretável no contexto da pesquisa.
```python
class_names = le.classes_

explainer = shap.TreeExplainer(treeForma)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test, feature_names=vect.get_feature_names_out(), plot_type='bar', class_names=class_names)
```
![image](https://github.com/user-attachments/assets/1b0438bb-daca-4cd0-9566-666beb72fd6c)

A variável com maior impacto nos resultados foi a resposta à pergunta "Decisão da empresa para modelo 100% presencial", especificamente a opção "Vou procurar outra oportunidade no modelo 100% remoto". Esse atributo, isoladamente, teve uma influência significativamente superior às demais variáveis, sobretudo na previsão da preferência por modelo 100% remoto. Em segundo lugar em importância, aparece o atributo "Forma de trabalho atual = Modelo 100% remoto", que também teve forte impacto, especialmente para a mesma classe. As demais variáveis — como idade, cargo, situação CLT, gênero, estado onde mora, entre outras — tiveram influência muito reduzida, praticamente irrelevante para o modelo. Além disso, é possível notar que a classe "Modelo 100% presencial" teve participação mínima nas decisões do modelo, o que sugere que, por conta do desbalanceamento dos dados, a árvore teve dificuldade em aprender padrões que levassem a essa predição.

### Testando o modelo com SMOTE
Com o objetivo de investigar como o modelo se comportaria em um cenário com dados mais balanceados, aplicamos a técnica SMOTE (Synthetic Minority Over-sampling Technique). Essa técnica é amplamente utilizada para lidar com desequilíbrios entre classes, criando novas amostras sintéticas para as classes minoritárias com base em seus vizinhos mais próximos, em vez de simplesmente replicar exemplos existentes.
```python
print("Antes do SMOTE:", Counter(y_train))
smt = SMOTE(sampling_strategy='not majority', random_state=42)
X_train, y_train = smt.fit_resample(X_train, y_train)
print("Depois do SMOTE:", Counter(y_train))
```
No nosso caso, a classe correspondente ao modelo de trabalho presencial era expressivamente minoritária em comparação às demais. Antes da aplicação do SMOTE, a distribuição era:
```
Antes do SMOTE: Counter({np.int64(2): 2019, np.int64(1): 1708, np.int64(0): 75})
```
Utilizando o parâmetro `sampling_strategy='not majority'`, o SMOTE gerou novas amostras para as classes menos representadas (presencial e remoto), igualando ela ao número de amostras da classe majoritária (modelo híbrido). O resultado foi:
```
Depois do SMOTE: Counter({np.int64(2): 2019, np.int64(1): 2019, np.int64(0): 2019})
```
Esse balanceamento foi aplicado apenas sobre o conjunto de treino, mantendo o conjunto de teste original para garantir uma avaliação realista da capacidade de generalização do modelo.

Após o reequilíbrio, o modelo foi treinado novamente seguindo a mesma configuração anterior. Observamos que a acurácia no **conjunto de treino subiu para 81%**, o que representa um ganho significativo. No entanto, a acurácia no **conjunto de teste caiu para 71%**, indicando uma possível perda de generalização, possivelmente causada pelo aumento de ruído introduzido pelas amostras sintéticas.
```
Acurácia no treino: 0.8104672280006604
Acurácia no teste: 0.7108307045215563
```
#### Classification Report e SMOTE
A análise do `classification_report` revelou que, apesar da tentativa de balanceamento, a classe minoritária (presencial) ainda apresentou desempenho insatisfatório. Embora tenha havido alguns acertos, os resultados continuam demonstrando forte confusão com a classe híbrida, dificultando a distinção entre esses dois regimes de trabalho.
```
              precision    recall  f1-score   support

           0       0.10      0.43      0.17        21
           1       0.76      0.74      0.75       416
           2       0.78      0.70      0.74       514

    accuracy                           0.71       951
   macro avg       0.55      0.62      0.55       951
weighted avg       0.76      0.71      0.73       951
```

Observa-se que houve uma melhora na capacidade do modelo em considerar as classes minoritárias, embora ainda existam limitações. A classe 0, que representa a menor quantidade de exemplos originalmente, apresentou um recall de 0.43, o que indica que 43% das amostras reais dessa classe foram corretamente identificadas pelo modelo. No entanto, sua precision permaneceu baixa (0.10), o que sugere que, embora mais instâncias dessa classe estejam sendo reconhecidas, muitas previsões feitas como sendo da classe 0 estão incorretas. Isso impacta diretamente o seu f1-score, que ficou em 0.17. 

Por outro lado, as classes 1 e 2 tiveram bons desempenhos, com precision, recall e f1-score em torno de 0.74 a 0.78, refletindo a maior quantidade de dados disponíveis e um impacto positivo do balanceamento em manter a estabilidade dessas previsões. A acurácia geral do modelo foi de 71%, mas a média macro dos escores (macro avg), que trata todas as classes com o mesmo peso, mostra um valor inferior (0.55), revelando que ainda há um desequilíbrio no tratamento das diferentes classes. Já a média ponderada (weighted avg), que leva em conta o número de amostras por classe, ficou próxima da acurácia total, em 0.73, o que reforça que o desempenho do modelo é majoritariamente sustentado pelas classes com maior representatividade. 

Em resumo, o uso do SMOTE trouxe ganhos ao permitir que o modelo reconhecesse melhor a classe 0, mas ainda é evidente que o desempenho para essa classe está aquém do ideal, exigindo possíveis ajustes no modelo ou na abordagem de balanceamento.

#### Matriz de confusão e SMOTE
Além disso, a matriz de confusão reforça esse comportamento, evidenciando que a redistribuição dos dados com SMOTE não foi suficiente para corrigir completamente o viés do modelo, embora tenha contribuído levemente para melhorar o reconhecimento da classe minoritária.
```
Matriz de confusão: 
[[  9   2  10]
 [ 16 309  91]
 [ 61  95 358]]
                             Prev=Modelo 100% presencial  Prev=Modelo 100% remoto  Prev=Modelo híbrido
Real=Modelo 100% presencial                            9   			2		    10
Real=Modelo 100% remoto                               16   		      309		    91
Real=Modelo híbrido                                   61   		       95		   358
```
![image](https://github.com/user-attachments/assets/12151bbb-8c0c-4f2b-ae0c-5cc235757837)

**Análise da Matriz de Confusão e SMOTE**

Após a aplicação da técnica SMOTE, foi possível observar uma leve melhora na capacidade do modelo de reconhecer a classe minoritária — o modelo de trabalho 100% presencial —, mas os resultados ainda demonstram limitações significativas. Antes do balanceamento, o modelo praticamente ignorava essa classe, apresentando recall igual a zero. Após o SMOTE, no entanto, o modelo passou a acertar 9 das 21 amostras dessa categoria, elevando o recall para 43%. Isso indica que, embora ainda longe do ideal, ao menos parte das instâncias presenciais passou a ser corretamente identificada.

Apesar desse avanço, a precisão da classe presencial permaneceu extremamente baixa, em torno de 10%. Ou seja, das vezes em que o modelo previu que determinada amostra era da classe 0 (presencial), apenas uma pequena fração estava realmente correta. Isso revela que o modelo ainda confunde frequentemente essa classe com as demais, especialmente com o modelo híbrido. Essa confusão impacta diretamente o f1-score da classe, que ficou em apenas 0.17 — um valor bastante inferior ao necessário para uma classificação confiável.

No conjunto como um todo, o SMOTE parece ter ajudado o modelo a manter um desempenho razoável para as classes mais representativas (remoto e híbrido), com valores de precisão, recall e f1-score acima de 70%. A acurácia geral no conjunto de teste, após o rebalanceamento, foi de 71%, o que representa uma leve queda em comparação ao modelo treinado com dados desequilibrados. Essa redução sugere uma possível perda de generalização, provavelmente causada pelo ruído introduzido pelas amostras sintéticas criadas artificialmente.

A matriz de confusão confirma essa análise. A maior parte dos erros cometidos pelo modelo ocorre entre as classes híbrida e remota, mas há também um volume expressivo de exemplos da classe presencial sendo classificados erroneamente como híbridos. Isso mostra que, mesmo com o SMOTE, o modelo ainda tem dificuldade em diferenciar com clareza o regime 100% presencial do híbrido — talvez por semelhanças nos padrões de dados ou pela escassez original de exemplos reais da classe presencial no conjunto de treino.

Em resumo, a aplicação do SMOTE foi eficaz para iniciar uma correção no viés do modelo contra a classe minoritária, permitindo que o modelo ao menos começasse a identificá-la. No entanto, a melhoria foi parcial e limitada, exigindo, para avanços mais expressivos, outros ajustes complementares, como testes com algoritmos diferentes, uso de outras técnicas de balanceamento, refinamento de features ou até um novo processo de coleta de dados mais equilibrado.

#### Importância dos atributos
Diferentemente do modelo treinado sem o uso do SMOTE, a análise da importância dos atributos mostrou uma distribuição mais diversificada entre as variáveis, indicando que o modelo passou a considerar um conjunto mais amplo de fatores na previsão da variável alvo.

![image](https://github.com/user-attachments/assets/6f3bb8eb-f14a-4962-99ff-2fccdfc7f4fc)

A análise da importância dos atributos no modelo Decision Tree revela que a variável mais relevante para a previsão da forma de trabalho ideal é a forma de trabalho atual, especialmente quando se trata do modelo 100% remoto, que apresenta o maior peso entre todos os atributos. Em seguida, a forma de trabalho atual como modelo híbrido e a intenção de procurar outra oportunidade caso a empresa adote o modelo 100% presencial (especificamente migrando para o trabalho remoto) também exercem forte influência na classificação. A forma de trabalho atual 100% presencial aparece em quarto lugar em importância, ainda que com impacto bem menor. A variável cor/raça (no caso, branca) e a área de formação na computação ou tecnologia também aparecem como influenciadoras, embora com peso mais discreto. Outras variáveis, como a decisão de mudar de empresa se a forma de trabalho for presencial, o tipo de cargo atual e a faixa salarial mais elevada, apresentam importâncias relativamente baixas, indicando menor contribuição para a decisão do modelo. Esses resultados reforçam a ideia de que as experiências e preferências atuais dos profissionais com relação ao modelo de trabalho exercem papel central na definição do que consideram ideal, enquanto características sociodemográficas ou ocupacionais específicas têm influência mais limitada.

#### SHAP e SMOTE
Outro aspecto importante a ser destacado foi a distribuição dos valores SHAP, que indicou que algumas variáveis realmente assumiram relevância específica na distinção da classe presencial. Isso demonstra que o modelo conseguiu identificar certos padrões associados a esse regime de trabalho. Contudo, essa relevância atribuída pelos valores SHAP não se traduziu em uma melhora significativa nos resultados práticos, como evidenciado pelo `classification_report` e pela matriz de confusão. Mesmo com o aumento da importância de determinados atributos, a performance da classe presencial permaneceu limitada, com acertos pontuais e uma forte confusão com o modelo híbrido. Isso sugere que, embora o modelo perceba diferenças sutis, essas distinções não são robustas o suficiente para garantir previsões confiáveis para essa classe minoritária.

![image](https://github.com/user-attachments/assets/7e861286-be5d-4112-b7ac-0c57232685b4)

O gráfico mostra o impacto médio de cada variável nas três classes previstas pelo modelo: “modelo 100% presencial”, “modelo 100% remoto” e “modelo híbrido”. Os resultados indicam que as experiências profissionais anteriores e as decisões relacionadas ao modelo de trabalho adotado pela empresa são os principais determinantes das preferências individuais.

Para os respondentes classificados como preferindo o modelo 100% presencial, o fator que mais influenciou negativamente foi o fato de já trabalharem no modelo 100% remoto. Isso sugere que quem já atua remotamente tem menor propensão a considerar o modelo presencial como ideal, o que é coerente com a hipótese de que a vivência em um modelo influencia a preferência futura. Além disso, a declaração de que buscariam outra oportunidade caso a empresa adotasse o modelo 100% presencial também teve um peso considerável, reforçando a ideia de rejeição ao formato exclusivamente presencial.

No caso daqueles classificados como preferindo o modelo 100% remoto, os atributos mais influentes foram o fato de já estarem inseridos em modelos de trabalho remoto ou híbrido, bem como a disposição de procurar outra vaga caso fossem obrigados a trabalhar presencialmente. A experiência prévia com modelos flexíveis de trabalho parece, portanto, reforçar o desejo de mantê-los. Já para os que preferem o modelo híbrido, o padrão se repete: a principal variável foi o fato de já trabalharem em um formato híbrido, seguido da resistência ao retorno completo ao presencial. Isso reforça a noção de que o histórico profissional recente molda diretamente as expectativas e preferências dos profissionais.

Em contraste, características demográficas e socioeconômicas como raça, gênero, faixa salarial, tempo de experiência, idade, e até mesmo o tempo dedicado a cuidados domésticos, tiveram influência bastante reduzida no modelo. Isso sugere que a preferência pela forma de trabalho ideal é explicada muito mais pelas vivências profissionais atuais e pelas percepções sobre decisões das empresas, do que por fatores estruturais como renda, cor ou gênero.

### Interpretação do Modelo 1

No primeiro teste, sem o uso do SMOTE, o modelo apresentou um desempenho razoável. Ele conseguiu identificar, com certa confusão, a maioria dos casos relacionados aos regimes híbrido e remoto. Essa confusão pode ser compreensível, já que, na prática, esses dois modelos de trabalho possuem características semelhantes, o que pode levar a uma sobreposição nos dados do conjunto de treino.

Já o regime presencial foi praticamente ignorado pelo modelo, o que pode ser explicado pela quantidade significativamente menor de exemplos dessa classe no conjunto de dados — apenas 96, contra cerca de 2.000 exemplos das classes remoto e híbrido.

Outro ponto relevante diz respeito à importância das variáveis. No teste sem balanceamento, o modelo baseou suas previsões quase exclusivamente em uma única variável, o que demonstra um certo viés. No entanto, após o uso do SMOTE para balancear as classes, o modelo passou a considerar mais variáveis e conseguiu prever uma quantidade razoável de exemplos da classe presencial, ainda que com desempenho modesto.

Mesmo assim, houve uma maior confusão entre híbrido, remoto e presencial — o que faz sentido, já que o modelo híbrido, por definição, é uma combinação dos outros dois, e isso pode dificultar a distinção entre as categorias com base apenas em variáveis preditoras.

Também é importante destacar que as variáveis mais relevantes para o modelo, tanto com quanto sem SMOTE, foram "como a pessoa trabalha atualmente" e "o que ela faria em caso de decisões da empresa". Já variáveis mais relacionadas ao perfil socioeconômico, como gênero, cor e salário, tiveram baixa importância nas previsões.

Em resumo, o modelo mostrou bom desempenho na identificação de padrões entre os regimes remoto e híbrido, mas teve dificuldade com a classe presencial, especialmente devido ao desbalanceamento dos dados. No entanto, isso não chega a ser um grande problema, pois, na prática, é comum que profissionais da área de dados tenham uma preferência maior pelo regime remoto, devido à flexibilidade que ele proporciona.


### Resultados obtidos com o modelo 2.

#### Resultados com Classification Report
Assim como no primeiro modelo, foi aplicado novamente o classification_report com o objetivo de avaliar o desempenho do classificador em relação a cada uma das classes do atributo-alvo, fornecendo métricas como precisão, recall e F1-score.
```python
# Visualização do classification_report
print(classification_report(y_test, y_pred))
```
```
            precision    recall  f1-score   support

           0       0.00      0.00      0.00        21
           1       0.78      0.69      0.73       416
           2       0.75      0.85      0.79       514

    accuracy                           0.76       951
   macro avg       0.51      0.51      0.51       951
weighted avg       0.75      0.76      0.75       951
```

Da mesma forma que acontece com o primeiro modelo, aqui a classe presencial (0) apresenta um baixo desempenho, enquanto as outras duas (remoto e híbrido) possuem desempenho significativamente melhor por estarem mais representadas na base de dados. Isso evidencia novamente o impacto do desbalanceamento entre as classes.

O desempenho geral do modelo Random Forest reforça esse desequilíbrio: a classe 0 (presencial) não é corretamente identificada em nenhuma instância — com precision, recall e f1-score iguais a 0 — mostrando que o modelo ignora completamente essa categoria. Já as classes 1 (remoto) e 2 (híbrido), mais frequentes, apresentam bons resultados, com destaque para a classe 2, que atinge recall de 0.85 e f1-score de 0.79.

Embora o accuracy total seja 76%, esse número esconde o fato de que o modelo acerta quase exclusivamente as classes majoritárias. A média macro das métricas é de apenas 0.51, revelando o fraco desempenho médio entre todas as classes, independentemente de seu tamanho.

#### Desenvolvimento da Matriz de Confusão
Além disso, a matriz de confusão foi gerada em três formatos distintos:
- Como matriz numérica bruta
- Formatada em um `DataFrame` com os nomes das classes para melhor compreensão,
- E como uma imagem utilizando `ConfusionMatrixDisplay`, o que facilita ainda mais a interpretação visual dos acertos e erros do modelo.
```python
# Matriz de confusão
cnf_matrix = confusion_matrix(y_test, y_pred)
print(f'Matriz de confusão: \n{cnf_matrix}')
```
```
Matriz de confusão: 
[[  0   2  19]
 [  0 288 128]
 [  0  78 436]]
```
```python
# Matriz de confusão formatada
df_cnf_matrix = pd.DataFrame(cnf_matrix, index=le.classes_, columns=le.classes_)
print(f'Matriz de confusão formatada: \n{df_cnf_matrix}')
```
```
                        Modelo 100% presencial  Modelo 100% remoto  Modelo híbrido
Modelo 100% presencial                       0                   2   		19
Modelo 100% remoto                           0                 288   	       128
Modelo híbrido                               0                  78   	       436
```
```python
# Gerando a matriz como uma imagem
display = ConfusionMatrixDisplay.from_estimator(forest, X_test, y_test, display_labels=le.classes_, cmap=plt.cm.Greens)

plt.xticks(rotation=90)
plt.show()
```
![image](https://github.com/user-attachments/assets/a7dca242-a007-4b18-be91-63d3b6d0be27)

**Análise da Matriz de confusão**

Com base nos resultados do segundo modelo treinado, mesmo sem a aplicação de técnicas de balanceamento como o SMOTE, observamos uma repetição clara do padrão de desempenho desigual entre as classes. A métrica de acurácia geral foi de 76%, um valor aparentemente satisfatório à primeira vista. No entanto, ao analisarmos o desempenho específico por classe, torna-se evidente que esse número mascara problemas significativos relacionados ao desbalanceamento da base de dados.

A classe 0 — correspondente ao modelo 100% presencial — continua sendo completamente ignorada pela Random Forest. O classification report revela que, para essa classe, tanto a precisão quanto o recall e o f1-score foram igual a zero. Isso significa que o modelo não conseguiu prever corretamente nenhuma das 21 amostras dessa classe, classificando-as erroneamente como pertencentes ao modelo remoto (classe 1) ou ao híbrido (classe 2). Essa falha é refletida também na matriz de confusão, onde se vê que 2 dessas amostras foram classificadas como remotas e 19 como híbridas.

Em contraste, as classes 1 (modelo remoto) e 2 (modelo híbrido) tiveram desempenho significativamente melhor. A classe remota apresentou precisão de 78%, recall de 69% e f1-score de 73%, enquanto a classe híbrida se destacou com recall de 85% e f1-score de 79%. A matriz de confusão confirma essa performance ao mostrar que o modelo acertou corretamente 288 amostras da classe remota e 436 da classe híbrida.

Apesar disso, a média macro — que calcula o desempenho médio entre todas as classes, tratando-as de forma igual — foi de apenas 0.51, refletindo o impacto negativo da ausência de acertos na classe minoritária. O modelo, portanto, tende a favorecer as classes mais representadas, o que é um comportamento comum quando o desequilíbrio entre as categorias não é tratado.

A visualização da matriz de confusão como imagem reforça essa leitura, deixando claro que o modelo ignora por completo a primeira classe. Esse tipo de viés pode ser particularmente problemático em aplicações reais, onde é fundamental que todas as categorias sejam reconhecidas, especialmente se a classe minoritária representa uma situação crítica ou específica que não pode ser negligenciada.

Em resumo, os resultados do segundo modelo confirmam a limitação estrutural da Random Forest ao lidar com dados desbalanceados. A acurácia geral alta é ilusória, e as métricas mais justas, como macro average e a própria matriz de confusão, revelam que o modelo falha completamente em reconhecer o regime de trabalho presencial. Isso evidencia a necessidade de aplicar técnicas de balanceamento, ajustes no modelo ou reestruturação da base para garantir uma classificação mais equitativa entre todas as categorias.

#### Importância dos atributos
Também foi exibida a importância das variáveis por meio do atributo `feature_importances_` do Random Forest. Para isso, utilizamos a função pd.Series para organizar as importâncias de forma ordenada e clara, seguida da plotagem de um gráfico de barras, permitindo visualizar quais atributos mais contribuíram para as decisões do modelo.
```python
importances = forest.feature_importances_

series = pd.Series(importances, index=vect.get_feature_names_out())
series = series.sort_values(ascending=False).head(10)

plt.figure(figsize=(5, 5))
series.plot(kind='barh', legend=False)
plt.title('Importância das variáveis')
plt.gca().invert_yaxis()
```
![image](https://github.com/user-attachments/assets/cf7921a7-dede-45f4-a410-2150fdb5426f)

A análise da importância das variáveis do modelo Random Forest revela que os principais fatores que influenciam a predição da “forma de trabalho ideal” estão diretamente relacionados à atual forma de trabalho dos profissionais e à sua reação frente à decisão das empresas de retornarem ao modelo 100% presencial. A variável com maior impacto foi a decisão de procurar outra oportunidade caso a empresa adote um modelo totalmente presencial, especificamente para quem busca manter o trabalho 100% remoto. Isso indica que o modelo reconhece uma forte associação entre a preferência por trabalho remoto e a recusa a retornar presencialmente.

Em seguida, a forma de trabalho atual — tanto no modelo remoto quanto no híbrido — também aparece como altamente relevante, sugerindo que a experiência atual do profissional influencia diretamente sua preferência futura. A aceitação ou não de retornar ao modelo 100% presencial também contribui significativamente, especialmente quando a resposta envolve procurar oportunidades híbridas ou remotas, demonstrando a importância da flexibilidade na decisão dos trabalhadores.

Por outro lado, variáveis como idade, nível de escolaridade não informado e cargo atual não informado apresentaram impacto mínimo nas previsões. Isso reforça a ideia de que, nesse modelo sem balanceamento de classes, o comportamento frente à política de trabalho da empresa e o modelo de trabalho atual são os elementos mais decisivos. Essa distribuição da importância das variáveis também ajuda a explicar o fraco desempenho do modelo para a classe presencial, visto que as variáveis mais relevantes favorecem fortemente as classes relacionadas ao trabalho remoto ou híbrido.

#### Visualização com SHAP
Por fim, foi utilizado o SHAP (SHapley Additive exPlanations) para gerar uma visualização que destaca a relevância de cada atributo na tomada de decisão do modelo para cada classe. Essa análise fornece uma camada adicional de interpretabilidade, essencial para compreender o impacto de cada variável no comportamento do modelo.
```python
class_names = le.classes_

explainer = shap.TreeExplainer(forest)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test, feature_names=vect.get_feature_names_out(), plot_type='bar', class_names=class_names)
```
![image](https://github.com/user-attachments/assets/6179e5e7-6646-48a9-b6d4-020a827493b2)

A análise dos valores SHAP para o modelo Random Forest mostra, de forma mais detalhada, o impacto médio de cada variável na predição das três classes de forma de trabalho ideal (modelo 100% remoto, híbrido e 100% presencial). Assim como observado anteriormente com a importância das variáveis, os fatores que mais influenciam o modelo são comportamentais e relacionados diretamente à opinião do profissional sobre decisões da empresa quanto ao retorno presencial.

As três variáveis de maior impacto para as predições — “Decisão da empresa para modelo 100% presencial = Vou procurar outra oportunidade no modelo 100% remoto”, “Forma de trabalho atual = Modelo 100% remoto” e “Forma de trabalho atual = Modelo híbrido” — exercem influência principalmente sobre as classes remota e híbrida, com destaque para a primeira, que tem grande peso na distinção entre quem prefere continuar em home office e quem aceita o modelo híbrido. Isso demonstra que o modelo reconhece que quem já trabalha remotamente e pretende sair caso haja retorno presencial tende fortemente a continuar preferindo o remoto.

A classe presencial, por sua vez, praticamente não é influenciada de forma relevante por nenhuma variável, como indicado pela presença limitada da cor verde (referente ao modelo presencial) nos gráficos. Isso evidencia a baixa capacidade do modelo em aprender padrões consistentes para prever essa classe, o que está alinhado ao desempenho anterior, onde a classe 0 (presencial) obteve métricas praticamente nulas.

Além disso, observa-se que variáveis como cargo, idade, gênero, região e faixa salarial possuem impacto muito pequeno, o que reforça a ideia de que a percepção individual frente ao modelo de trabalho é mais decisiva do que atributos demográficos ou profissionais. A ausência do uso de SMOTE neste modelo contribui para esse desequilíbrio, fazendo com que as classes mais representadas (remoto e híbrido) sejam priorizadas no processo de decisão.

#### Testando o modelo com SMOTE
Aplicamos a mesma sequência de códigos utilizada no primeiro modelo para avaliar o desempenho do modelo após o uso do SMOTE, com o objetivo de verificar se houve alguma melhora na identificação da classe minoritária. Essa abordagem permitiu uma comparação direta dos resultados, mantendo a consistência metodológica ao longo da análise.
```python
print("Antes do SMOTE:", Counter(y_train))
smt = SMOTE(sampling_strategy='not majority', random_state=42)
X_train, y_train = smt.fit_resample(X_train, y_train)
print("Depois do SMOTE:", Counter(y_train))
```
```
Antes do SMOTE: Counter({np.int64(2): 2019, np.int64(1): 1708, np.int64(0): 75})
```
```
Depois do SMOTE: Counter({np.int64(2): 2019, np.int64(1): 2019, np.int64(0): 2019})
```
Esse balanceamento foi aplicado apenas sobre o conjunto de treino, mantendo o conjunto de teste original para garantir uma avaliação realista da capacidade de generalização do modelo.

No caso do Random Forest, após a aplicação do SMOTE, observamos um comportamento divergente entre os conjuntos de treino e teste. Embora a acurácia no treinamento tenha aumentado para 81%, indicando que o modelo conseguiu aprender melhor os padrões com os dados balanceados, a acurácia nos dados de teste caiu para 69%. Esse resultado sugere um possível overfitting, no qual o modelo se ajusta excessivamente aos dados de treino, mas perde capacidade de generalização ao lidar com novos dados.
```
Acurácia do treinamento: 0.8131087997358428
Acurácia do teste: 0.6971608832807571
```
#### Classification Report e SMOTE
A análise do `classification_report` revelou que, apesar da tentativa de balanceamento, a classe minoritária (presencial) ainda apresentou desempenho insatisfatório. Embora tenha havido alguns acertos, os resultados continuam demonstrando forte confusão com a classe híbrida, dificultando a distinção entre esses dois regimes de trabalho.
```
              precision    recall  f1-score   support

           0       0.11      0.43      0.17        21
           1       0.71      0.79      0.75       416
           2       0.80      0.63      0.71       514

    accuracy                           0.70       951
   macro avg       0.54      0.62      0.54       951
weighted avg       0.75      0.70      0.71       951
```
Com a aplicação do SMOTE (Synthetic Minority Over-sampling Technique), observamos uma melhora significativa no desempenho da classe minoritária (classe 0 – presencial), que anteriormente havia apresentado resultados praticamente nulos. Neste novo cenário, a classe 0 atinge um recall de 0.43, o que significa que o modelo passou a identificar corretamente uma quantidade considerável de exemplos dessa classe. No entanto, a precision ainda é bastante baixa (0.11), indicando que muitos exemplos previstos como "presencial" na verdade pertencem a outras classes. O f1-score da classe 0 ficou em 0.17, o que ainda é modesto, mas representa um avanço em relação ao modelo anterior sem SMOTE.

As classes 1 (modelo híbrido) e 2 (modelo remoto), que são majoritárias, continuam apresentando bons desempenhos. A classe 1 possui precision de 0.71 e recall de 0.79, enquanto a classe 2 tem precision de 0.80 e recall de 0.63. Isso mostra um pequeno ajuste nas predições, com o modelo sacrificando parte da performance das classes majoritárias para compensar o maior equilíbrio na classificação da classe minoritária. O f1-score geral das classes 1 e 2 permanece robusto (0.75 e 0.71, respectivamente).

O accuracy geral do modelo caiu ligeiramente para 70% (em comparação com 76% no modelo sem SMOTE), mas esse decréscimo é esperado e aceitável diante do ganho de equilíbrio entre as classes. As médias macro de precision e f1-score (0.54) também indicam que o modelo está lidando melhor com a distribuição desigual das classes, refletindo o impacto positivo do SMOTE na justiça do modelo.

Em resumo, a introdução do SMOTE ajudou o modelo Random Forest a reconhecer e considerar melhor a classe "presencial", contribuindo para uma distribuição de erros mais equilibrada entre as classes. Ainda há espaço para melhorias — especialmente na precisão da classe 0 — mas o resultado representa um avanço em termos de representatividade e justiça na predição.

#### Matriz de confusão e SMOTE
Além disso, a matriz de confusão reforça esse comportamento, evidenciando que a redistribuição dos dados com SMOTE não foi suficiente para corrigir completamente o viés do modelo, embora tenha contribuído levemente para melhorar o reconhecimento da classe minoritária.
```
Matriz de confusão: 
[[  9   4   8]
 [ 14 330  72]
 [ 59 131 324]]
Matriz de confusão formatada: 
                        Modelo 100% presencial  Modelo 100% remoto  Modelo híbrido
Modelo 100% presencial                       9                   4   		 8
Modelo 100% remoto                          14                 330   		72
Modelo híbrido                              59                 131   	       324
```
![image](https://github.com/user-attachments/assets/3df14cc7-096b-4e03-b6db-89ca9b23e967)

**Análise da Matriz de Confusão e SMOTE**

Com a aplicação da técnica de balanceamento SMOTE (Synthetic Minority Over-sampling Technique), o modelo Random Forest demonstrou avanços significativos na identificação da classe minoritária (modelo 100% presencial), embora ainda apresente limitações importantes.

A matriz de confusão obtida após a aplicação do SMOTE, juntamente com os dados do classification report, evidenciam esse progresso. Anteriormente ignorada pelo modelo, a classe 0 agora passa a ser reconhecida com mais frequência: dos 21 exemplos dessa classe, 9 foram corretamente classificados como "presencial", resultando em um recall de 0.43 — um aumento considerável em relação ao recall nulo nos modelos anteriores. No entanto, a precision permanece extremamente baixa (0.11), o que significa que o modelo frequentemente classifica instâncias de outras categorias como sendo da classe presencial, gerando falsos positivos. Isso reflete na persistente dificuldade do modelo em delimitar claramente os contornos entre os perfis "presencial" e "híbrido", como revelado na matriz de confusão: ainda há significativa confusão entre essas duas classes.

A performance das classes majoritárias sofreu uma leve queda, como era esperado. O modelo 100% remoto (classe 1) manteve bons níveis de desempenho, com precisão de 0.71 e recall de 0.79, enquanto a classe híbrida (classe 2) apresentou precisão de 0.80 e recall de 0.63. Essa redistribuição do foco do modelo, mais equitativa entre as três classes, causou uma leve diminuição no accuracy geral, que caiu de 76% para 70%. No entanto, essa queda é compensada pelo ganho de justiça no reconhecimento das diferentes classes.

A média macro das métricas (0.54 para precision e f1-score) reflete essa melhora no equilíbrio entre as categorias, indicando que o modelo agora leva mais em consideração a classe minoritária na hora de aprender e fazer previsões. Ainda assim, é importante notar que a classe 0 continua sendo a mais desafiadora para o modelo, tanto em termos de precisão quanto de f1-score (apenas 0.17), apontando que, embora o SMOTE tenha reduzido o viés, ele não resolveu completamente a dificuldade de classificação.

A matriz de confusão final ilustra bem esse comportamento: os erros do modelo estão mais distribuídos e não concentrados exclusivamente na classe minoritária, como antes. O número de classificações corretas aumentou para a classe presencial, e as demais classes seguem com bons níveis de acerto, apesar de um leve aumento nos erros de confusão.

Em resumo, a aplicação do SMOTE trouxe um avanço concreto no reconhecimento da classe presencial, demonstrando ser uma estratégia eficaz para mitigar os efeitos do desbalanceamento de dados. Ainda há espaço para melhorias — principalmente no refinamento da precisão da classe minoritária —, mas o modelo se torna mais justo e equilibrado ao considerar de forma mais apropriada todas as categorias do atributo-alvo.

#### Importância dos atributos e SMOTE
Assim como no primeiro modelo, a aplicação do SMOTE no Random Forest resultou em uma redistribuição da importância dos atributos, conferindo maior diversidade às variáveis consideradas relevantes pelo modelo. No entanto, essa mudança não foi tão expressiva quanto a observada anteriormente.

![image](https://github.com/user-attachments/assets/526d81bc-0dfc-4b17-a404-4de34a7ec471)

A variável mais influente é “Forma de trabalho atual = Modelo 100% remoto”, seguida por “Forma de trabalho atual = Modelo 100% presencial” e “Decisão da empresa para modelo 100% presencial = Vou procurar outra oportunidade no modelo 100% remoto”. Isso indica que a experiência recente da pessoa com o modelo de trabalho e sua disposição para continuar ou mudar de empresa diante de decisões unilaterais da organização são determinantes importantes no modelo.

A presença da variável “Forma de trabalho atual = Modelo híbrido” também com peso considerável reforça esse padrão: o histórico de trabalho do profissional está diretamente ligado à sua forma de trabalho ideal.

Além disso, variáveis como a decisão de procurar outra oportunidade caso a empresa imponha o retorno presencial e a disposição de aceitar retornar ao modelo presencial também aparecem com destaque, o que mostra que a flexibilidade ou resistência ao trabalho presencial está fortemente associada às preferências futuras.

Entre os fatores sociodemográficos, temos “Cor/Raça = Branca”, “Nível de ensino = Pós-graduação”, “Faixa salarial de R$8.001 a R$12.000” e “Horas com trabalho doméstico e cuidado”, que embora com menor impacto, ainda contribuem para a decisão final do modelo. Isso sugere que características socioeconômicas e contextos pessoais também têm influência, embora secundária, nas preferências de forma de trabalho.

O uso do SMOTE contribuiu para distribuir melhor o peso das variáveis entre as classes, permitindo que o modelo considerasse com mais equilíbrio diferentes perfis de trabalhadores — inclusive aqueles com menor representação na base original, como os que preferem o trabalho 100% presencial. A importância atribuída às variáveis se mostra coerente com os principais fatores que afetam a decisão sobre o modelo ideal de trabalho, destacando tanto aspectos subjetivos (preferência e experiência) quanto estruturais (nível de escolaridade, renda e carga de cuidados).

#### SHAP e SMOTE
Da mesma forma, a visualização com SHAP indicou que o modelo passou a atribuir maior importância a variáveis associadas à classe minoritária. No entanto, esse comportamento não se traduziu em uma melhoria concreta na performance, já que a matriz de confusão continuou apresentando dificuldades na correta classificação dos casos presenciais, demonstrando que o problema de confusão entre as classes persiste.

![image](https://github.com/user-attachments/assets/ca1562b0-f1e0-4f53-9142-318193141ad0)

A variável mais influente no modelo é a “Forma de trabalho atual = Modelo 100% remoto”. Ela exerce grande impacto especialmente nas previsões de preferência por modelo remoto e, em menor grau, por modelo híbrido. Isso indica que profissionais que atualmente trabalham de forma totalmente remota tendem a preferir continuar nesse formato ou migrar para um híbrido, demonstrando forte associação entre a experiência atual de trabalho e a preferência futura.

A segunda variável mais importante é a “Decisão da empresa para modelo 100% presencial = Vou procurar outra oportunidade no modelo 100% remoto”. Essa variável representa uma postura de resistência ao retorno obrigatório ao presencial e está fortemente associada a predições de preferência por modelos mais flexíveis. Em outras palavras, o simples fato de uma pessoa indicar que buscaria outro emprego diante de um retorno forçado ao presencial já é um forte indicativo de que ela idealiza o trabalho remoto.

A “Forma de trabalho atual = Modelo 100% presencial” também aparece entre as variáveis de maior importância, estando associada principalmente à previsão de preferência pelo mesmo modelo. Isso reforça a tendência de que muitos profissionais preferem manter a configuração atual de trabalho, talvez por hábito, adaptação ou identificação com o modelo vigente.

Outras variáveis relacionadas às atitudes frente à imposição de retorno ao trabalho 100% presencial — como “vou procurar outra oportunidade no modelo híbrido ou remoto” e “vou aceitar e retornar” — também possuem papel importante. Isso sugere que mais do que o perfil sociodemográfico, o modelo valoriza fortemente a forma como os profissionais se posicionam diante de mudanças nas políticas de trabalho das empresas. A forma de trabalho atual e a reação a cenários hipotéticos são, assim, os elementos mais preditivos das preferências.

Embora fatores como raça/cor, nível de ensino, faixa salarial, gênero, tempo de experiência e responsabilidades domésticas também estejam presentes no modelo, seu impacto é bem menor. Essas variáveis aparecem mais abaixo no ranking de importância, mostrando que, neste contexto, o comportamento e a experiência recente com o trabalho (especialmente a flexibilidade) são muito mais relevantes do que características pessoais.

A análise geral indica que a preferência pela forma ideal de trabalho está fortemente associada à vivência atual e ao desejo de manter a autonomia sobre o modelo adotado. O modelo não se baseia tanto em atributos sociais, mas sim na forma como os indivíduos experienciam e reagem à flexibilização (ou falta dela) no ambiente profissional.

### Interpretação do modelo 2

Assim como ocorreu com o Modelo 1, o Modelo 2 — baseado em Random Forest — seguiu uma lógica semelhante em relação à classificação dos regimes de trabalho. Ele teve bom desempenho na previsão das classes híbrido e remoto, mas falhou ao identificar corretamente a classe presencial, que foi praticamente ignorada. Esse comportamento é compreensível, considerando que os modelos híbrido e remoto compartilham características semelhantes, o que pode confundir o modelo. Além disso, o Random Forest é uma evolução do modelo de árvore de decisão, o que naturalmente leva a resultados parecidos em termos de padrões capturados.

Uma diferença importante em relação ao Modelo 1 foi a distribuição da importância das variáveis. Enquanto o primeiro modelo demonstrou viés ao considerar quase exclusivamente uma única variável, o Random Forest (sem SMOTE) foi capaz de atribuir importância a um conjunto mais diverso de variáveis. As mais relevantes foram o modelo de trabalho atual da pessoa e o que ela faria caso a empresa adotasse o regime 100% presencial. Por outro lado, variáveis socioeconômicas como gênero, cor e salário novamente tiveram pouca relevância.

A análise com SHAP reforçou esse cenário: as variáveis relacionadas ao contexto de trabalho foram muito influentes na classificação das categorias híbrido e remoto, mas tiveram pouca influência na classe presencial.

É importante destacar que, neste experimento, mantivemos os mesmos parâmetros utilizados no Modelo 1, com o objetivo de permitir uma comparação direta entre os modelos. No entanto, isso pode ter limitado o desempenho da Random Forest, que poderia ter se beneficiado de uma melhor calibragem dos hiperparâmetros. Com o uso do SMOTE, o desempenho do modelo na identificação da classe presencial melhorou ligeiramente, mas ainda ficou abaixo do esperado. Acreditamos que, com ajustes mais adequados nos parâmetros ou melhorias na base de dados, o modelo poderia apresentar resultados significativamente melhores.

Após o balanceamento com SMOTE, o SHAP indicou uma maior diversidade nas variáveis consideradas importantes, incluindo algumas socioeconômicas. Ainda assim, as variáveis relacionadas diretamente ao contexto de trabalho continuaram sendo as mais influentes. Além disso, observamos que algumas variáveis específicas passaram a ter um papel relevante na previsão da classe presencial, o que pode ser um bom sinal para futuros ajustes no modelo, mesmo que ainda ocorra uma margem de erro considerável.

Em resumo, o Random Forest apresentou potencial para obter resultados mais robustos, especialmente se ajustado adequadamente. Sua natureza mais robusta contra overfitting, combinada com sua capacidade de considerar múltiplas variáveis, sugere que ele pode, com melhorias, capturar de forma mais precisa as preferências dos profissionais em relação ao regime de trabalho, mesmo diante de confusões entre as classes.

### Análise Comparativa dos Modelos

Concluindo a análise comparativa entre os dois modelos — Decision Tree e Random Forest — podemos observar que ambos apresentaram desempenho semelhante no que diz respeito à classificação das categorias híbrido e remoto, mas enfrentaram dificuldades significativas para prever corretamente a classe presencial, especialmente quando os dados estavam desbalanceados. Essa limitação é explicável, considerando que o número de exemplos presenciais no conjunto de dados era bastante inferior em relação às outras duas classes, além do fato de que os regimes híbrido e remoto compartilham características semelhantes, o que naturalmente gera confusão nos padrões identificados pelos modelos.

A Decision Tree, sem o uso do SMOTE, mostrou-se mais enviesada, baseando suas previsões quase exclusivamente em uma única variável, o que limita sua capacidade de generalização. Já o Random Forest, mesmo com os mesmos parâmetros do modelo anterior, conseguiu distribuir melhor a importância entre diferentes variáveis, o que o torna um modelo mais robusto e interpretável. A aplicação do SMOTE trouxe melhorias para ambos os modelos, especialmente na capacidade de identificar a classe presencial, ainda que de forma modesta. Contudo, o Random Forest demonstrou um aproveitamento mais consistente desse balanceamento, aumentando a diversidade das variáveis relevantes — incluindo, ainda que em menor grau, variáveis socioeconômicas — enquanto manteve como principais fatores os relacionados diretamente ao contexto de trabalho da pessoa.

A análise com SHAP reforçou essas observações: embora os dois modelos tenham apresentado maior influência de variáveis na previsão das categorias híbrido e remoto, ambos também conseguiram atribuir alguma importância à classe presencial. No entanto, essa importância observada nas explicações dos modelos não se refletiu de maneira satisfatória na matriz de confusão, o que indica que, embora os modelos estivessem captando alguns sinais relevantes, eles ainda não foram suficientes para uma previsão precisa dessa classe. Isso sugere que há potencial para melhoria, especialmente se forem inseridas variáveis mais discriminativas ou adotadas estratégias de ajuste mais refinadas.

Em conclusão, o modelo Random Forest demonstrou maior potencial para capturar padrões diversos e apresentar resultados mais equilibrados, sendo mais indicado para tarefas preditivas que exigem robustez e menor risco de overfitting. A Decision Tree, apesar de sua simplicidade e maior interpretabilidade, mostrou-se mais limitada diante da complexidade dos dados analisados. Ainda assim, ambos os modelos poderiam apresentar resultados melhores com ajustes nos hiperparâmetros, ampliação da base de dados (especialmente para a classe presencial) e refinamento na seleção ou criação de variáveis mais representativas. Essas melhorias permitiriam uma previsão mais precisa e equilibrada entre as diferentes categorias de regime de trabalho.

### Distribuição do modelo
Para distribuir o modelo, utilizamos o Flask para criar um servidor que executa os dois modelos treinados com SMOTE, selecionados por apresentarem os melhores desempenhos.
Todos os arquivos necessários para o funcionamento do servidor estão localizados na pasta: [`assets/models/distrib_model`](https://github.com/ICEI-PUC-Minas-PPL-CDIA/ppl-cd-pcd-sist-int-2025-1-workregime-2025-1/tree/main/assets/models/distrib_model)

#### Como executar o servidor
1. Instale as dependências listadas no arquivo requirements.txt utilizando o comando:
```
pip install -r requirements.txt
```
2. Inicie o servidor Flask executando o seguinte comando no terminal:
```
python app.py
```
![image](https://github.com/user-attachments/assets/08fd7d4f-2cb9-4161-93d2-0ce5b3886e8d)

A porta será definida automaticamente. Após iniciar o servidor, será exibido um endereço IP no terminal. Você pode acessá-lo diretamente no navegador, digitando o IP ou clicando com Ctrl + clique no link.

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

**João Vitor de Lima**

Desde o início, este projeto apresentou desafios, especialmente na formulação de uma pergunta orientada a dados viável e na escolha de variáveis compatíveis com a base principal, a “State of Data”. A proposta inicial era prever quatro categorias de regime de trabalho — híbrido fixo, híbrido flexível, remoto e presencial — mas, para melhorar a performance dos modelos, optamos por unificar os dois tipos de híbrido, reduzindo as classes para: híbrido, remoto e presencial.

Foram então desenvolvidos dois modelos preditivos: uma Árvore de Decisão e uma Random Forest. Ambos apresentaram desempenho razoável, com cerca de 70% de acurácia. No entanto, a classe “presencial” teve baixa taxa de acerto, reflexo direto de sua sub-representação na base. A matriz de confusão se mostrou crucial para essa análise: inicialmente difícil de interpretar, acabou sendo fundamental para identificar os padrões de erro, especialmente na confusão recorrente entre as classes híbrido e remoto.

Também testamos bases complementares, mas sua contribuição foi limitada. Faltaram variáveis mais contextuais — como tempo de deslocamento ou rotina familiar — que poderiam ter aumentado a precisão dos modelos. Entendemos que esses dados são mais sensíveis, mas sua ausência compromete parte da análise.

Apesar das limitações, o processo foi valioso. Fomos ajustando rotas ao longo do caminho, aprofundando a compreensão dos modelos e aprendendo com os erros. Se fosse possível refazer o estudo, começaríamos com uma seleção mais criteriosa das variáveis e bases, além de buscar um maior equilíbrio entre as classes, especialmente o regime presencial.

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
[`assets/models`](https://github.com/ICEI-PUC-Minas-PPL-CDIA/ppl-cd-pcd-sist-int-2025-1-workregime-2025-1/tree/main/assets/models)

Dos artefatos (armazenado do repositório);
[`src`](https://github.com/ICEI-PUC-Minas-PPL-CDIA/ppl-cd-pcd-sist-int-2025-1-workregime-2025-1/tree/main/src)

Da apresentação final (armazenado no repositório);

[Vídeo de apresentação](https://youtu.be/V4XIr8OAF04)
