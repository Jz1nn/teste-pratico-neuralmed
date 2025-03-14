# Análise de Documentos Médicos com NLP

## 1. Análise Descritiva dos Documentos

### Observações Iniciais
Os documentos médicos são escritos em diferentes formatos: HTML, RTF e texto simples. A maioria dos documentos está em formato HTML (4253), seguido por RTF (1852) e texto simples (729).

### Distribuição dos Pacientes
**Total de registros:** 6834

**Distribuição por sexo:**
- Feminino (F): 3986 registros
- Masculino (M): 2788 registros
- Indefinido (I): 60 registros

**Distribuição etária:**
- Média de idade: 49.24 anos
- Desvio padrão: 21.96 anos
- Idade mínima: 2 anos
- Idade máxima: 101 anos

### Termos Mais Frequentes
**Comorbidades mais comuns:**
- HAS (Hipertensão Arterial Sistêmica): 1438 ocorrências
- DM (Diabetes Mellitus): 1195 ocorrências
- IAM (Infarto Agudo do Miocárdio): 518 ocorrências
- TVP (Trombose Venosa Profunda): 372 ocorrências
- Obesidade: 225 ocorrências

**Ações Médicas mais comuns:**
- Exame: 2122 ocorrências
- Prescrição: 697 ocorrências
- TC (Tomografia Computadorizada): 631 ocorrências
- Cirurgia: 626 ocorrências
- USG (Ultrassonografia): 609 ocorrências

**Queixas mais comuns:**
- Dor: 2470 ocorrências
- Febre: 475 ocorrências
- Desconforto: 193 ocorrências
- Vômito: 74 ocorrências
- Náusea: 52 ocorrências

### Conclusões
Os documentos são escritos em diferentes formatos e contêm informações sobre os pacientes, incluindo comorbidades, ações médicas e queixas. A análise dos termos mais frequentes mostra que muitos pacientes apresentam condições semelhantes como: hipertensão, diabetes e são submetidos a exames e cirurgias.

## 2. Extração de Informações de Medicamentos, Exames e Doenças

### Pipeline de Desenvolvimento

**Pré-processamento dos Dados:**
- Limpeza dos textos para remover caracteres especiais, tags HTML e RTF.
- Expansão de abreviações médicas para termos completos.

**Anotação de Entidades:**
- Utilização de um modelo de NLP (spaCy) para identificar entidades de medicamentos, exames e doenças.
- Criação de padrões para dosagens e frequências de medicamentos.

**Treinamento do Modelo:**
- Utilização do BERTimbau, um modelo de linguagem pré-treinado, para classificação multi-rótulo.
- Divisão dos dados em conjuntos de treino e validação.
- Treinamento do modelo com os textos pré-processados e as entidades anotadas.

**Validação do Modelo:**
- Avaliação do modelo utilizando métricas como F1-score e acurácia.
- Ajuste de hiperparâmetros e re-treinamento conforme necessário.

## 3. Extração via Prompt

### Tipos de Prompt
- **Medicamentos:** Extrair nomes de medicamentos, dosagens e frequências.
- **Doenças:** Identificar doenças mencionadas e seus sintomas associados.
- **Exames:** Listar exames solicitados, data e resultados.
- **Abreviações:** Expandir abreviações médicas para termos completos.
- **Diagnóstico:** Predizer doenças, medicamentos prescritos e exames solicitados.