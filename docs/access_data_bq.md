# Como usar via BigQuery

Basta acessar o projeto no BiqQuery e escrever sua query para explorar os dados.

## Acessando o projeto

??? info "Como crio uma conta gratuita no BigQuery?"
    É preciso ter uma conta no Google para acessar. Ao clicar
    no botão abaixo você será redirecionado para logar na sua conta ou
    criar uma antes de acessar o projeto.

    O site deve solicitar que você crie um projeto qualquer no seu BigQuery 
    antes de acessar os nossos dados - não se preocupe, não é pago! O BigQuery 
    inicia automaticamente no modo Sanbox, que permite você utilizar sem adicionar 
    um modo de pagamento. Leia mais sobre o Sandbox [aqui](https://cloud.google.com/bigquery/docs/sandbox).

<a
href="https://console.cloud.google.com/bigquery?p=basedosdados&page=project"
title="{{ lang.t('source.link.title')}}" class="md-button"
style="background-color: var(--md-primary-fg-color);color:
var(--md-primary-bg-color);"
hover="background-color: var(--md-primary-fg-color--dark)">
    Clique para acessar o projeto no BigQuery
</a>

Dentro do projeto existem dois níveis de organização, <strong style="color:#007aa7">*datasets*</strong>
(conjuntos de dados) e <strong style="color:#4b00a7">*tables*</strong>
(tabelas), nos quais:

- Todas as *tables* estão organizadas em *datasets*
- Cada *table* pertence a um único *dataset*

!!! Info "Caso não apareçam as tabelas nos *datasets* do projeto, atualize a página."
    

![](images/bq_structure.png){ width=100% }


## Explorando os dados

### Exemplo

!!! Tip "Teste: Quais os municípios *millennials* 🕶?"
    Rode a query no `Editor de consultas` e descubra municípios criados nos anos 2000.

```sql
SELECT *
FROM `basedosdados.br_suporte.diretorio_municipios`
WHERE existia_2000 = 0;
```

### Metadados

Clicando num *dataset* ou *table* você já consegue ver toda a estrutura
e descrição das colunas, e pode acessar também os detalhes de tratamento e publicação,
como frequência de atualização, autor da publicação e do tratamento dos dados.

![](images/bq_schema_details.png){ width=100% }

### Buscando os dados

O BigQuery possui já um mecanismo de busca que permite buscar por nomes
de *datasets* (conjuntos), *tables* (tabelas) ou *labels* (grupos).

!!! Tip "Construímos uma regras de nomeação simples e práticas para facilitar sua busca"
    Veja como é essa estrutura [na seção de Nomenclatura](../naming_rules/).

### Construindo sua query

Clicando no botão `🔍 Query View`, o BigQuery cria automaticamente a estrutura básica
da sua query em `Query Editor` - basta você completar com os campos e filtros que achar
necessários.

![](images/bq_query_view.png){ width=100% }

!!! Info "O BigQuery utiliza SQL como linguagem nativa. Leia mais sobre a sintaxe utilizada [aqui](https://cloud.google.com/bigquery/docs/reference/standard-sql/query-syntax)"
