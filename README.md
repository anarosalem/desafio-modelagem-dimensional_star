# Construção de um Modelo Dimensional (Star Schema) no Power BI 🌟

## Objetivo do Projeto
O objetivo deste desafio foi aplicar os conceitos de modelagem dimensional para transformar uma tabela única de dados financeiros (Financial Sample) num **Esquema em Estrela (Star Schema)**. Foram criadas tabelas Fato e Dimensão, promovendo uma estrutura otimizada para análise e performance no Power BI.

## Processo de Construção do Diagrama
A partir da tabela principal, foi gerada uma cópia de segurança inativa (`financials_origem`). Posteriormente, a tabela ativa foi duplicada várias vezes no **Power Query** para isolar as características específicas de cada dimensão. 
- Utilizou-se o recurso de **Coluna Condicional** para criar chaves de identificação (ex: `ID_Produto` atribuindo valores inteiros para cada tipo de produto)[cite: 4].
- A tabela `D_Produtos` foi gerada através da função **Agrupar Por**, calculando agregações matemáticas cruciais como Média, Mediana, Valor Máximo e Valor Mínimo das vendas[cite: 4].
- Nas restantes tabelas dimensão (`D_Descontos`, `D_Produtos_Detalhes`), as colunas redundantes foram eliminadas e os dados duplicados removidos para garantir a integridade relacional[cite: 4].
- Na Tabela Fato (`F_Vendas`), foi adicionada uma **Coluna de Índice** para servir como chave primária (`SK_ID`) do registo de vendas[cite: 4].

## Funcionalidades e Funções DAX Utilizadas
Para complementar as informações temporais ausentes nas dimensões derivadas do Power Query, foi criada a tabela **D_Calendário**.
- **Função DAX Utilizada:** `D_Calendario = CALENDARAUTO()`[cite: 4]. Esta função varre o modelo em busca de datas e cria um calendário contínuo automaticamente, o que é fundamental para futuras análises de Inteligência Temporal (Time Intelligence).

## Como Visualizar
1. Consulte a imagem `esquema_estrela.png` anexada neste repositório para visualizar a topologia do modelo construído[cite: 4].
2. O projeto completo pode ser explorado ao descarregar o ficheiro `.pbix` e aceder à aba de Modelo no Power BI Desktop[cite: 4].
