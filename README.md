# 📊 Dashboard de Conformidade Documental e Revisão Normativa

<p align="center">
  <strong>Power BI • DAX • ETL • SharePoint • Business Intelligence</strong>
</p>

> ⚠️ Projeto desenvolvido para fins de portfólio.
>
> Algumas informações foram anonimizadas e adaptadas para preservar a confidencialidade dos dados, processos internos e informações organizacionais.

---

## 📑 Índice

- Sobre o Projeto
- Contexto e Problema de Negócio
- Primeira Versão da Solução
- Reestruturação e Otimização Completa do Projeto
- Automatização da Atualização dos Dados
- Tratamento e Transformação dos Dados
- Modelagem dos Dados
- Colunas Desenvolvidas
- Indicadores Desenvolvidos
- Funcionalidades do Dashboard
- Desafios Encontrados
- Resultados Obtidos
- Tecnologias Utilizadas
- Principais Aprendizados
- Autor
- Licença

---

# 📖 Sobre o Projeto

Este projeto foi desenvolvido por **Rennan de Oliveira Penga** durante minha atuação na área de Governança, Riscos, Controles Internos e Segurança.

O objetivo foi criar uma solução em Power BI capaz de monitorar a conformidade documental da organização, acompanhar o ciclo de revisão normativa e disponibilizar indicadores que apoiassem a tomada de decisão.

A proposta consistiu em transformar dados distribuídos em múltiplas planilhas Excel em uma plataforma analítica centralizada, permitindo identificar documentos vencidos, acompanhar documentos sem data de validade, monitorar áreas críticas e analisar a evolução dos indicadores ao longo do tempo.

Além de fornecer uma visão executiva da situação documental da organização, o dashboard também possibilita análises operacionais e históricas de forma prática e intuitiva.

---

# 🎯 Contexto e Problema de Negócio

Os dados utilizados eram recebidos por meio de extrações periódicas em Excel.

Apesar de conterem informações semelhantes, os arquivos apresentavam diversos problemas que dificultavam as análises:

- Estruturas diferentes entre as extrações;
- Colunas com nomenclaturas distintas;
- Registros duplicados;
- Campos nulos;
- Informações inconsistentes;
- Documentos sem data de validade;
- Necessidade de comparação entre períodos históricos.

Essas inconsistências aumentavam o esforço manual necessário para consolidar os dados e dificultavam a obtenção de indicadores confiáveis.

O desafio era transformar esse processo em uma solução escalável, automatizada e capaz de gerar informações estratégicas para o negócio.

---

# 🏗️ Primeira Versão da Solução

A primeira versão do dashboard foi construída a partir de três extrações realizadas em datas diferentes.

Como cada base possuía diferenças estruturais, foi necessário realizar diversos tratamentos para consolidar as informações.

Para acompanhar a evolução dos dados ao longo do tempo, foi criada uma coluna chamada **Data de Análise**, responsável por identificar a qual extração cada documento pertencia.

Após a consolidação dos dados, foram criadas medidas em DAX, indicadores, segmentações e visuais que permitiram monitorar a conformidade documental da organização.

Embora a solução atendesse às necessidades iniciais, o crescimento da base e a necessidade de ajustes constantes acabaram tornando o modelo mais complexo do que o necessário.

Ao longo do desenvolvimento, algumas tabelas foram duplicadas e diversos merges foram realizados para resolver necessidades pontuais dos dados. Embora funcionassem corretamente, essas abordagens aumentaram o tamanho do arquivo e o tempo de processamento.

---

# 🚀 Reestruturação e Otimização Completa do Projeto

Durante a manutenção do dashboard, percebi que seria mais eficiente reconstruir completamente a solução do que continuar realizando correções sobre a estrutura existente.

A nova versão teve como objetivo:

- Reduzir a complexidade do modelo;
- Melhorar a performance;
- Facilitar a manutenção;
- Automatizar a atualização dos dados;
- Tornar a solução escalável para futuras expansões.

Toda a estrutura foi revisada, incluindo consultas, relacionamentos, medidas e processos de atualização.

Também foram removidos processos redundantes, merges desnecessários e tabelas que não agregavam valor ao modelo analítico.

---

# 🔄 Automatização da Atualização dos Dados

Uma das maiores melhorias implementadas foi a automação do processo de atualização.

Na versão anterior, a atualização podia consumir aproximadamente **4 horas** entre importação, tratamento e validação dos dados.

Na nova arquitetura, foi criada uma integração com SharePoint.

O processo passou a funcionar da seguinte forma:

1. Baixar a nova extração de dados;
2. Salvar o arquivo em uma pasta específica do SharePoint;
3. Atualizar o Power BI.

Foi criada uma consulta responsável por buscar automaticamente todos os arquivos presentes na pasta de dados.

Além disso, a própria data de criação dos arquivos no SharePoint passou a ser utilizada como referência da análise.

Como os arquivos são enviados no mesmo dia da extração dos dados, deixou de ser necessário criar manualmente uma coluna de Data de Análise para cada atualização.

O resultado foi um processo muito mais rápido, organizado e fácil de manter.

---

# 📊 Estrutura do Dashboard

A solução foi desenvolvida com foco em monitoramento de conformidade documental e acompanhamento de indicadores regulatórios.

O dashboard é composto por quatro páginas principais:

### 📈 Página Executiva

Apresenta uma visão consolidada dos indicadores de conformidade documental, possibilitando acompanhamento estratégico dos resultados.

### ⚠️ Documentos Vencidos

Página dedicada à análise detalhada dos documentos fora do prazo de validade, incluindo classificações por atraso e identificação das áreas mais críticas.

### 🔥 Top 50 Documentos Mais Visualizados

Permite identificar os documentos mais acessados pela organização e acompanhar sua situação de conformidade.

### 📄 Documentos Sem Data de Validade

Apresenta documentos sem validade cadastrada, auxiliando na identificação de inconsistências e oportunidades de melhoria cadastral.

---

# 🧹 Tratamento e Transformação dos Dados

A preparação dos dados foi realizada utilizando Power Query.

As principais etapas incluíram:

- Importação automática dos arquivos;
- Padronização dos nomes das colunas;
- Ajuste dos tipos de dados;
- Tratamento de valores nulos;
- Remoção de registros duplicados;
- Consolidação das bases históricas;
- Ajustes em arquivos com estruturas antigas;
- Simplificação de merges e transformações existentes.

Uma das bases históricas possuía uma estrutura diferente das demais e exigiu um tratamento específico para manter a compatibilidade com o restante do modelo.

Durante a reconstrução do dashboard, também foi criada uma abordagem mais eficiente para organização dos dados, reduzindo dependências desnecessárias entre consultas e facilitando futuras atualizações.

---

# 🗂️ Modelagem dos Dados

Com os dados consolidados, foi construída uma modelagem mais organizada e performática.

Foi criada uma tabela de dimensão contendo:

- Áreas responsáveis pelos documentos;
- Gerências executivas correspondentes;
- Relacionamentos necessários para filtros e indicadores.

Essa abordagem reduziu a redundância de informações, melhorou a organização do modelo e facilitou a navegação dos usuários pelos indicadores.

A estrutura permitiu a criação de filtros hierárquicos mais intuitivos e melhor desempenho na atualização dos dados.

---

# ⚙️ Colunas Desenvolvidas

Durante a reconstrução do modelo, diversas transformações que anteriormente eram realizadas no Power Query passaram a ser realizadas utilizando DAX, reduzindo a complexidade do ETL e tornando a manutenção mais simples.

### Informação da Data de Validade

Responsável por identificar se o documento possui ou não uma data de validade cadastrada.

Classificações:

- Com Data
- Indeterminado

### Dias Vencidos

Calcula automaticamente quantos dias um documento está vencido em relação à data da análise.

Essa coluna foi desenvolvida para facilitar a identificação de documentos críticos e apoiar a priorização das ações corretivas.

### Tipo de Documento

Separa a sigla do identificador do documento.

Exemplo:

```text
AB-0001
```

Resultado:

```text
AB
```

### Número Sequencial

Extrai a parte numérica do identificador.

Resultado:

```text
0001
```

### Categoria do Documento

Converte a sigla do documento em sua categoria correspondente.

Exemplo:

```text
AB → Análise Biológica
```

### Status de Vigência

Classifica automaticamente a situação documental.

Categorias:

- Em Dia;
- Vence em até 30 dias;
- Vencido há mais de 12 meses;
- Vencido há mais de 6 meses;
- Vencido há mais de 3 meses;
- Vencido há mais de 1 mês;
- Vencido há menos de 1 mês;
- Indeterminado.

Essas classificações foram utilizadas em indicadores, gráficos e formatações condicionais para facilitar a interpretação das informações pelos usuários.

---

# 📏 Indicadores Desenvolvidos

Durante o projeto foram criadas diversas medidas em DAX para atender aos requisitos do negócio.

### ICCRNC

Indicador responsável por medir o percentual de documentos dentro do prazo de validade.

### ICCRNC Descumprimento

Indicador responsável por medir o percentual de documentos vencidos.

### Top 50 Documentos Mais Visualizados

Ranking criado para identificar os documentos mais acessados e monitorar sua situação de conformidade.

### Indicadores de Criticidade

Métricas desenvolvidas para identificar áreas com maior quantidade e percentual de documentos vencidos.

### Formatação Condicional

Medidas responsáveis pela alteração dinâmica de:

- Cores dos indicadores;
- Textos;
- Cartões;
- Tabelas;
- Elementos visuais.

Essa abordagem permitiu destacar automaticamente situações críticas e facilitar a análise dos resultados.

---

# 📊 Funcionalidades do Dashboard

## 📈 Página Executiva

Visão consolidada da situação documental da organização.

Funcionalidades:

- Indicadores gerais de conformidade;
- Filtros por área;
- Filtros por gerência executiva;
- Percentual de documentos em dia e vencidos;
- Evolução histórica dos indicadores;
- Ranking das áreas mais críticas.

---

## ⚠️ Documentos Vencidos

Página dedicada à análise detalhada dos documentos fora do prazo de validade.

Funcionalidades:

- Ranking das áreas com maior quantidade de documentos vencidos;
- Classificação por faixa de atraso;
- Visualização dos documentos mais críticos;
- Quantidade de dias vencidos por documento.

---

## 🔥 Top 50 Documentos Mais Visualizados

Página desenvolvida para identificar os documentos mais relevantes para o negócio.

Funcionalidades:

- Ranking dos 50 documentos mais acessados;
- Identificação visual da situação de vigência;
- Exibição do identificador único dos documentos.

---

## 📄 Documentos Sem Data de Validade

Página criada para identificar inconsistências cadastrais relacionadas à validade documental.

Funcionalidades:

- Quantidade de documentos sem validade cadastrada;
- Distribuição por categoria documental;
- Agrupamento por tipo de documento;
- Apoio à regularização dos registros.

---

# 💡 Desafios Encontrados

Um dos principais desafios do projeto foi a apresentação dos detalhes dos documentos através de tooltips.

Inicialmente, o objetivo era apresentar listas completas de documentos diretamente nas dicas de ferramenta dos gráficos.

Porém, devido ao grande volume de registros, a navegação se tornou limitada, prejudicando a experiência dos usuários.

Como solução, foram criadas páginas específicas acessadas através de botões de navegação, permitindo visualizar informações detalhadas sem comprometer a usabilidade do dashboard.

Além disso, a necessidade de reconstrução completa da solução serviu como uma importante oportunidade de aprendizado relacionada à otimização de modelos de dados, simplificação de processos de ETL e automação de atualizações.

---

# 📈 Resultados Obtidos

✅ Atualização reduzida de aproximadamente 4 horas para poucos minutos.

✅ Processo de atualização praticamente automatizado.

✅ Integração automatizada com SharePoint.

✅ Redução significativa da complexidade do modelo.

✅ Melhor desempenho dos relatórios.

✅ Menor esforço de manutenção.

✅ Estrutura mais organizada e escalável.

✅ Melhor experiência para os usuários.

✅ Maior confiabilidade dos indicadores.

✅ Maior facilidade para futuras expansões do projeto.

A evolução do dashboard transformou uma solução inicialmente funcional em uma plataforma analítica mais robusta, escalável e preparada para crescimento.

---

# 🛠️ Tecnologias Utilizadas

| Tecnologia | Utilização |
|------------|------------|
| Power BI | Desenvolvimento dos dashboards |
| DAX | Indicadores e medidas |
| Power Query | ETL e transformação de dados |
| SharePoint | Automação e armazenamento |
| Excel | Fonte de dados |
| SQL | Consultas e tratamento de dados |
| Python | Automações e análises complementares |
| Data Modeling | Estrutura analítica |
| Data Visualization | Construção dos visuais |

---

# 📚 Principais Aprendizados

Durante o desenvolvimento deste projeto, aprofundei conhecimentos em:

- Power BI;
- DAX;
- Power Query;
- ETL;
- Modelagem de Dados;
- Integração com SharePoint;
- Automação de Processos;
- Otimização de Performance;
- Desenvolvimento de KPIs;
- Governança de Dados;
- Data Visualization;
- UX para Dashboards;
- Tomada de Decisão Baseada em Dados.

Além das habilidades técnicas, o projeto reforçou a importância de projetar soluções escaláveis desde o início, reduzindo a complexidade de manutenção e melhorando a experiência dos usuários finais.

---

# 👨‍💻 Autor

**Rennan de Oliveira Penga**

Estudante de Análise e Desenvolvimento de Sistemas (ADS) com foco em Análise de Dados, Business Intelligence e Automação de Processos.

Tenho experiência com Power BI, SQL, Python, modelagem de dados, ETL e desenvolvimento de soluções orientadas por dados para apoiar a tomada de decisão e a melhoria de processos organizacionais.

### 🔗 Contatos

- GitHub: https://github.com/rehkkj
- LinkedIn: https://linkedin.com/in/rennan-oliveira-426320283
- E-mail: rennanpenga@gmail.com

---

# 📄 Licença

Este projeto está licenciado sob a **MIT License**.

Consulte o arquivo `LICENSE` para mais informações.
