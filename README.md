# Projeto Drupal - Gerenciamento de Cachoeiras e Parques de Diversão

Este projeto foi desenvolvido em Drupal e tem como objetivo criar uma plataforma de gerenciamento para **Cachoeiras** e **Parques de Diversão**. O sistema inclui a instalação de módulos essenciais, criação de tipos de conteúdo, taxonomias, views, blocos personalizados e configurações para exibição dinâmica de conteúdo.

## Módulos Utilizados

O projeto utiliza os seguintes módulos para facilitar a administração e personalização do Drupal:

- **Admin Toolbar**: Melhora a navegação no painel de administração.
- **Pathauto**: Gera URLs amigáveis automaticamente para os conteúdos criados.
- **Token**: Permite o uso de variáveis dinâmicas.
- **Devel**: Ferramentas de desenvolvimento para geração de conteúdo fictício.
- **Drush**: Interface de linha de comando para facilitar a administração do Drupal.

Esses módulos foram instalados e ativados via **Composer**:

```bash
composer require drupal/admin_toolbar drupal/pathauto drupal/token drupal/devel drupal/drush
```

## Tipos de Conteúdo Criados

### 1. **Cachoeiras**
Este tipo de conteúdo foi configurado com os seguintes campos:

- **Nome**: Título da cachoeira (campo `title`).
- **Descrição**: Descrição detalhada da cachoeira (campo `body`).
- **Site Oficial**: Link externo para o site oficial.
- **Instruções para Acesso**: Campo de texto com instruções para acesso.
- **Altura**: Altura da cachoeira em metros (campo numérico).
- **Imagem**: Imagem representativa da cachoeira.
- **Localização**: Referência para a taxonomia de **localizações** (campo de seleção).
- **Dificuldade**: Referência para a taxonomia de **dificuldades** (campo de seleção).

### 2. **Parques de Diversão**
Este tipo de conteúdo foi configurado com campos adequados para parques de diversão, incluindo:

- **Nome**: Nome do parque (campo `title`).
- **Descrição**: Descrição do parque (campo `body`).
- **Foto**: Imagem do parque.
- **Localização**: Referência para a taxonomia de **locais**.
- **Atrações Principais**: Campo de texto ou lista de atrações do parque.
- **Categoria**: Referência para a taxonomia de **categorias** (Ex: Aventura, Infantil).

## Taxonomias Criadas

Foram criadas as seguintes taxonomias para categorizar os conteúdos:

- **Localizações**: Para categorizar as cachoeiras e os parques por regiões.
- **Dificuldades**: Para categorizar as cachoeiras com níveis como Fácil, Médio e Difícil.
- **Categorias**: Para categorizar os parques de diversão, como Aventura, Infantil, etc.

## Configuração de URL

Padrões de URL foram configurados para os tipos de conteúdo:

- **Cachoeiras**: `/cachoeira/%`
- **Parques de Diversão**: `/parque/%`

Esses padrões garantem URLs amigáveis e estruturadas para fácil acesso.

## Views Criadas

Para exibir os conteúdos de maneira organizada e dinâmica, foram criadas as seguintes **views**:

- **Todas as Cachoeiras**: Exibe todas as cachoeiras cadastradas. Link adicionado ao menu principal.
- **Todos os Parques**: Exibe todos os parques cadastrados. Link adicionado ao menu principal.
- **Últimas 3 Cachoeiras**: Exibe as últimas 3 cachoeiras cadastradas. Exibido em um bloco no layout.
- **Últimos 3 Parques**: Exibe os últimos 3 parques cadastrados. Exibido em um bloco no layout.

## Blocos Criados

Blocos dinâmicos foram criados para exibir informações relevantes no layout da página:

- **Últimas 3 Cachoeiras**: Bloco exibindo as 3 últimas cachoeiras, com nome e local, além de link para detalhes.
- **Últimos 3 Parques**: Bloco exibindo foto, nome, local e link para a página de detalhes do parque.
- **Cachoeiras Relacionadas por Dificuldade**: Bloco exibindo cachoeiras com a mesma dificuldade, utilizando filtros contextuais para não exibir a cachoeira atual.

Os blocos foram posicionados nas regiões apropriadas do tema.

## Geração de Conteúdo

Conteúdos fictícios foram gerados utilizando o módulo **Devel** para testar a plataforma:

- 20 conteúdos de **Cachoeiras**
- 15 conteúdos de **Parques de Diversão**

Esses conteúdos foram gerados de forma automatizada para simular um ambiente de produção.

## Layout Personalizado com Layout Builder

O **Layout Builder** foi utilizado para personalizar a exibição das páginas de conteúdo. Isso inclui a modificação de layouts padrão, adição de blocos personalizados e ajuste da estrutura de exibição para otimizar a apresentação.

## Exportação de Configurações

Todas as configurações do projeto foram exportadas utilizando o **módulo de gerenciamento de configurações** do Drupal:

```bash
drush config-export
```

Isso gerou um diretório contendo todas as configurações exportadas, o que facilita a migração e versão das configurações em diferentes ambientes.

## Backup do Banco de Dados

O banco de dados foi exportado utilizando o **Drush** e salvo na pasta `database`:

```bash
drush sql-dump --result-file=database/database.sql
```

# Imagens

## Home
![image](https://github.com/user-attachments/assets/e393429a-8723-46ef-ba7b-5031fed09f64)

![image](https://github.com/user-attachments/assets/6c46eab7-dff3-4e42-be46-fc1674b02724)

![image](https://github.com/user-attachments/assets/73dec8e1-6112-49df-994a-be224c16fa00)

## Parque de Diversão

![image](https://github.com/user-attachments/assets/b68de8da-37f8-4f45-ba52-b795f3a0f5ce)

## Cachoeira

![image](https://github.com/user-attachments/assets/bb1e3d34-587c-42d8-ab9b-7012907a1ed7)

