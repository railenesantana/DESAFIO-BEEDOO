# DESAFIO-BEEDOO

Plano de teste: https://docs.google.com/spreadsheets/d/1rOLPmGJglk9G03M85TN4lr8e1fiPWkIGx5YcK2_cwFM/edit?usp=sharing
Controle de Bugs: https://docs.google.com/spreadsheets/d/1fGhqWWYCphBMzrLGBZhtTWo4l3xe6k9lETJEpA-9A8M/edit?usp=sharing
Evidências no Google Drive: https://drive.google.com/drive/folders/1Q5brCGgkXaA5OreX9dlMqoDAJaFCkH1Q?usp=drive_link

## Funcionalidade: Cadastrar curso 

### User Story 1
- **Eu**: como usuário da aplicação Beedoo Challenge
- **Gostaria**: de cadastrar um novo curso
- **Porque**: assim eu adiciono novos cursos ao sistema

### Regras de Negócio
- **RN 1**: Tela de Cadastro: A tela de cadastro deve ser acessível a partir do header, com a opção CADASTRAR CURSO.
  - **Campos Obrigatórios**: O formulário de cadastro deve incluir os seguintes campos obrigatórios:
    - Todos os cursos devem ser exibidos com informações completas.
    - Informações obrigatórias, seguindo a seguinte ordem:
      - Abaixo da imagem de capa, exibir a avaliação geral do curso entre 1.0 e 5.0, para o caso de usuários já terem realizado o curso, terá a avaliação exibida na lista.
      - Tipo do curso: Presencial ou Online.
      - Nome do curso.
      - Nome e Sobrenome do professor do curso.
      - Nota de avaliação do curso.
      - Descrição do curso (primeiros 215 caracteres) com opção para ver mais, caso a descrição ultrapasse o limite de 215 caracteres).
      - Data de início e final no formato: dd/mm/aaaa.
      - Número de vagas.
      - Valor do curso.
      - Se for curso presencial, incluir o endereço completo (rua, bairro, número, cidade e estado).
      - Incluir link de inscrição para curso Online e Presencial.
- **RN 2**: O sistema não deve permitir o cadastro de um curso com todas as informações obrigatórias de forma duplicada. Se o curso cadastrado pelo usuário tiver as mesmas informações obrigatórias, o sistema deve emitir uma mensagem informando: "Não é permitido o cadastro de cursos duplicados na plataforma, por favor, verifique!".
- **RN 3**: Nome do Header: Deve ter o nome Beedoo QA Challenge no lado esquerdo.
  - **Opções no Header**: Deve ter as opções LISTAR CURSOS e CADASTRAR CURSO no lado direito, um ao lado do outro, e em letras maiúsculas.
  - **Cor do Header**: O header deve ter a cor de fundo #FF9800. Os textos dos botões "Cadastrar Cursos" e "Listar Cursos" e o título "Beedoo QA Challenge" devem ter a cor branca.
- **RN 4**: No Formulário de Cadastro Título do Formulário: No topo do formulário de preenchimento de cadastro, deve ter o nome "Cadastro de curso" na cor #000000.
- **RN 5**: Todos os campos obrigatórios (inputs e dropdowns) devem ser preenchidos para que o cadastro do curso seja permitido.
- **RN 6**: No formulário de cadastro de curso deve ter um botão de "Cadastrar curso" associado.
- **RN 7**: Ao cadastrar um curso, deve ter uma mensagem obrigatória: "Curso cadastrado com sucesso!".
- **RN 8**: A interface da página do sistema deve ser responsiva, funcionando corretamente em diferentes tipos de dispositivos móveis e desktop.
- **RN 9**: O layout deve ser claro e fácil de navegar, com etiquetas (labels) apropriadas e botões intuitivos.
- **RN 10**: Se qualquer campo obrigatório estiver vazio, o cadastro do curso não será permitido e uma mensagem indicando que todos os campos obrigatórios devem ser preenchidos antes de prosseguir deve ser exibida.
- **RN 11**: O sistema não deve conter erros ortográficos.
- **RN 12**: Quando o usuário clicar para recarregar a página de curso através de seu próprio navegador, a página deve carregar sem erros no sistema do site Beedoo QA Challenge.

### Critérios de Aceite
- **CA 1**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** visualizo a área de cadastro de curso e preencho todos os campos obrigatórios 
  - **Então** o curso é cadastrado no sistema e exibido na listagem de cursos.
- **CA 2**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** visualizo a área de cadastro de curso e deixo os campos obrigatórios vazios 
  - **Então** o curso não é cadastrado no sistema e uma mensagem de erro indicando que todos os campos obrigatórios devem ser preenchidos é exibida.
 
## Funcionalidade: Validação de URL da Imagem da Capa

### User Story 2
- **Como**: usuário da aplicação Beedoo Challenge
- **Eu gostaria**: de inserir uma URL para a imagem da capa do curso
- **Porque**: assim posso adicionar uma imagem para a capa do curso

### Regras de Negócio
- **RN 1**: A URL da imagem da capa deve começar com `https://` e ter extensão `.jpg`, `.jpeg`, ou `.png`.
- **RN 2**: O campo de URL não deve conter apenas números.
- **RN 3**: Se o valor do campo de input URL inserido for apenas números, caracteres especiais, formato `http`, ou qualquer extensão de imagem que não seja `.jpg`, `.jpeg` ou `.png`, o sistema deve exibir o toast de erro: "Dados inválidos, por favor, verifique!"
- **RN 4**: Abaixo do campo URL de imagem da capa deve ter uma mensagem informativa, com a seguinte mensagem: "A URL deve começar com https://. Os tipos de imagens de capas aceitas são em formato: .jpg, .jpeg, ou .png."
- **RN 5**: Ao clicar para recarregar a página referente à funcionalidade Cadastrar curso, a página deve carregar corretamente e sem erros.

### Critérios de Aceite
- **CA 1**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** insiro uma URL válida para a imagem da capa que começa com `https://` e tem a extensão adequada 
  - **Então** a URL é aceita e o curso é cadastrado com a imagem.
- **CA 2**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** insiro uma URL que não começa com `https://` ou que não tem a extensão adequada 
  - **Então** o sistema exibe uma mensagem de erro: "O valor informado é inválido!"
- **CA 3**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** recarrego a página de cadastro de cursos 
  - **Então** a página recarrega corretamente sem erros no sistema.

## Funcionalidade: Validação das Datas

### User Story 3
- **Como**: usuário da aplicação Beedoo Challenge
- **Eu gostaria**: de definir datas de início e fim para o curso
- **Porque**: preciso garantir que o curso tenha um período de realização válido.

### Regras de Negócio
- **RN 1**: A data de início deve ser válida e não pode estar no passado; a data de fim deve ser após a data de início.
- **RN 2**: A data deve estar em formato padrão dd/mm/aaaa.

### Critérios de Aceite
- **CA 1**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** insiro uma data de início e uma data de fim válidas 
  - **E** a data de fim é posterior à data de início
  - **Então** o curso é cadastrado com as datas corretamente.
- **CA 2**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** insiro uma data de início que está no passado ou uma data de fim que é anterior à data de início 
  - **Então** o sistema exibe uma mensagem de erro indicando a validade das datas.

## Funcionalidade: Campos Dinâmicos com Base no Tipo de Curso

### User Story 4
- **Como**: usuário da aplicação Beedoo Challenge
- **Eu gostaria**: de ver campos adicionais com base no tipo de curso selecionado
- **Porque**: preciso fornecer informações específicas dependendo se o curso é presencial ou online.

### Regras de Negócio
- **RN 1**: Se o tipo de curso selecionado for Presencial, deve ser exibido o campo de input para o usuário inserir o endereço do curso.
- **RN 2**: Para curso Presencial e Online, deve ser exibido um campo para o usuário inserir o link de inscrição do curso.

### Critérios de Aceite
- **CA 1**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** seleciono Presencial como tipo de curso 
  - **Então** o campo para inserir o endereço do curso e o link de inscrição devem ser exibidos.
- **CA 2**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** seleciono Online como tipo de curso 
  - **Então** o campo para inserir o link de inscrição do curso deve ser exibido.
 
  ## Funcionalidade: Validação do Número de Vagas

### User Story 5
- **Como**: usuário da aplicação Beedoo Challenge
- **Eu gostaria**: de definir a quantidade de vagas disponíveis para o curso
- **Porque**: preciso especificar quantas vagas estão abertas para inscrição

### Regras de Negócio
- **RN 1**: O campo número de vagas deve ser um número inteiro positivo maior que zero e não deve aceitar caracteres especiais.

### Critérios de Aceite
- **CA 1**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** insiro um número inteiro positivo maior que zero no campo de vagas 
  - **Então** o número de vagas é aceito e o curso é cadastrado.
- **CA 2**: 
  - **Dado** que estou na aplicação Beedoo Challenge 
  - **Quando** insiro um número zero, negativo ou com caracteres especiais no campo de vagas 
  - **Então** o sistema exibe uma mensagem de erro informando: "Valor inválido!"

## Funcionalidade: Visualizar lista de cursos

### User Story 6
- **Como**: um usuário da aplicação Beedoo Challenge
- **Eu gostaria**: de visualizar a lista de cursos
- **Porque**: quero saber quais cursos estão disponíveis na plataforma

### Regras de Negócio
- **RN 1**: Se houver cursos cadastrados, a lista de cursos deve ser exibida na página de lista de cursos.
- **RN 2**: A interface deve ser responsiva, funcionando corretamente em diferentes tipos de dispositivos móveis e desktop.
- **RN 3**: No topo do formulário de preenchimento de cadastro, deve ter o nome "Lista de cursos" na cor #000000.
- **RN 4**: O layout deve ser claro e fácil de navegar, com etiquetas (labels) apropriadas e botões intuitivos.
- **RN 5**: Todos os cursos devem ser exibidos com informações completas. Informações obrigatórias, seguindo a seguinte ordem:
  - Abaixo da imagem de capa, exibir a avaliação geral do curso entre 1.0 e 5.0, para o caso de usuários já terem realizado o curso terá a avaliação exibida na lista.
  - Tipo do curso: Presencial ou Online.
  - Nome do curso.
  - Nome e Sobrenome do professor do curso.
  - Nota de avaliação do curso.
  - Descrição do curso (primeiros 215 caracteres) com opção para ver mais, caso a descrição ultrapasse o limite de 215 caracteres.
  - Data de início e final no formato: dd/mm/aaaa.
  - Número de vagas.
  - Valor do curso.
  - Se for curso presencial, incluir o endereço completo (rua, bairro, número, cidade e estado).
  - Incluir link de inscrição para curso Online e Presencial.
- **RN 6**: Limite de Cursos por Página: Se o número total de cursos exceder 10, a paginação deve ser ativada.
  - Adicionar Botão Próximo: 
    - Visibilidade: Exibido se houver mais de uma página.
    - Função: Navega para a próxima página de cursos.
    - Habilidade: Ativado se houver uma página seguinte; desativado na última página.
  - Adicionar Botão Voltar: 
    - Visibilidade: Exibido se houver mais de uma página.
    - Função: Navega para a página anterior de cursos.
    - Habilidade: Ativado se houver uma página anterior; desativado na primeira página.
- **RN 7**: Botão de Filtro:
  - Adicione um botão de filtro à página de lista de cursos.
  - Ao clicar, exiba opções para filtrar por Mais Populares e Classificação Mais Alta.
  - Filtros:
    - Mais Populares: Filtra cursos com base na popularidade.
    - Classificação Mais Alta: Filtra cursos pela avaliação mais alta.
    - Os filtros devem ser combináveis.
  - Botões de filtro exibidos no topo da página abaixo da regra número 5.
- **RN 8**: Adicionar um botão de "Editar curso" ao lado do botão de "Excluir curso", para que o usuário consiga editar e salvar as informações.
  - Deve ser aberta uma caixa com inputs na mesma página, estilo modal com as informações previamente do formulário de cadastro.
  - Ao final da modal deve ter um botão de "Salvar" e deve ser exibida uma mensagem obrigatória: "As alterações foram realizadas com sucesso!"
- **RN 9**: Adicionar uma caixa de formulário de pesquisa com input para pesquisa do usuário, à direita da caixa com o botão de envio do formulário de pesquisa com a lupa.
  - Quando o usuário inserir um texto, clicar na lupa na caixa de pesquisa.
  - Dentro da caixa insira um texto informativo, com a mensagem "Insira o nome do curso aqui".
  - Quando o usuário inserir um texto, essa mensagem some da caixa de pesquisa e ficará somente o texto que o usuário informou.
  - Se não houver nada relacionado à pesquisa do usuário, o sistema deve retornar: "Não foram encontrados resultados relacionados à sua busca!"
- **RN 10**: Se não houver cursos cadastrados na lista da página, o sistema deve exibir uma mensagem clara e visível informando que não há cursos disponíveis. A mensagem deve ser: "Nenhum curso disponível no momento."

### Critérios de Aceite
- **CA 1**:
  - **Dado** que estou na aplicação Beedoo Challenge
  - **Quando** eu acesso a página de lista de cursos
  - **Então** o sistema deve exibir a lista de cursos cadastrados com as informações essenciais do curso, incluindo detalhes específicos para cursos se for presencial ou online.
- **CA 2**:
  - **Dado** que estou na aplicação Beedoo Challenge
  - **Quando** eu acesso a página de lista de cursos
  - **E** o sistema não tem cursos cadastrados disponíveis
  - **Então** é exibida uma mensagem informando que não há cursos disponíveis no momento.

## Funcionalidade: Atualização em tempo real da lista de cursos

### User Story 7
- **Como**: um usuário da aplicação Beedoo Challenge
- **Eu gostaria**: que a lista de cursos fosse atualizada em tempo real
- **Porque**: quero ver as alterações imediatamente, como novos cursos adicionados ou cursos removidos

### Regras de Negócio
- **RN 1**: A lista de cursos deve ser atualizada em tempo real para refletir alterações, como novos cursos adicionados ou cursos removidos.
- **RN 2**: Dado que estou na aplicação Beedoo Challenge, quando um curso é adicionado ou removido, então a lista de cursos deve ser atualizada automaticamente para refletir essa alteração.

### Critérios de Aceite
- **CA 1**:
  - **Dado** que estou na aplicação Beedoo Challenge
  - **Quando** um curso é adicionado ou removido
  - **Então** a lista de cursos deve ser atualizada automaticamente para refletir essa alteração.

 ## Funcionalidade: Confirmação antes de excluir curso

### User Story 8
- **Como**: um usuário da aplicação Beedoo Challenge
- **Eu gostaria**: de receber uma confirmação antes de excluir um curso
- **Porque**: quero evitar excluir cursos acidentalmente

### Regras de Negócio
- **RN 1**: Texto e Botão de Exclusão
  - Exibir o texto "Presencial" ou "Online" abaixo da capa do curso.
  - Adicionar um botão "Excluir curso" com ícone de lixeira, posicionado ao final do link de inscrição do curso.
  - Blocos Informativos
    - Nome do curso e a Descrição: posicionar abaixo do tipo de curso.
    - Elementos: Data de início, Data de fim e Quantidade de vagas.
    - Estilo: Usar `<span>` com `display: block` para cada informação.
    - Acessibilidade: Garantir contraste de cores de todos os textos mencionados sejam adequado para legibilidade.
- **RN 2**: Ao clicar no botão "Excluir curso" associado a um curso, o sistema deve exibir uma caixa de diálogo de confirmação. A mensagem deve perguntar: "Tem certeza de que deseja excluir este curso? Esta ação não pode ser desfeita." A caixa de diálogo deve oferecer duas opções: Confirmar e Cancelar.
- **RN 3**: Se o usuário clicar em Confirmar, o curso deve ser removido da lista e o sistema deve atualizar a exibição.
- **RN 4**: Se o usuário clicar em Cancelar, nenhuma alteração deve ser feita e o curso deve permanecer na lista.
- **RN 5**: Após confirmar a exclusão, deve ser exibida uma mensagem informando: "Curso excluído com sucesso!"

### Critérios de Aceite
- **CA 1**:
  - **Dado** que estou na aplicação Beedoo Challenge
  - **Quando** eu clico no botão "Excluir curso" associado a um curso escolhido
  - **Então** o sistema deve exibir uma caixa de diálogo de confirmação com as opções Confirmar e Cancelar.
- **CA 2**:
  - **Dado** que estou na aplicação Beedoo Challenge
  - **Quando** eu confirmo a exclusão de um curso
  - **Então** o curso deve ser removido da lista
  - **E** deve ser exibida uma mensagem de sucesso.
- **CA 3**:
  - **Dado** que estou na aplicação Beedoo Challenge
  - **Quando** eu cancelo a exclusão de um curso
  - **Então** nenhuma alteração deve ser feita
  - **E** o curso deve permanecer na lista.

# Resumo das Decisões para Criação de User Stories

### Funcionalidade: Cadastrar Curso
- **PO**: Definiu campos obrigatórios e regras de validação.
- **Desenvolvimento**: Implementou a lógica de cadastro e validação.
- **Design**: Criou o layout da página de cadastro.
- **QA**: Testou o processo de cadastro e validou a usabilidade.

### Funcionalidade: Validação da URL da Imagem da Capa
- **PO**: Estabeleceu regras para a URL da imagem e mensagens de erro.
- **Desenvolvimento**: Implementou a validação da URL.
- **Design**: Desenvolveu a interface para inserção da URL e mensagens informativas.
- **QA**: Testou a validação da URL e mensagens de erro.

### Funcionalidade: Validação das Datas
- **PO**: Definiu validação para datas e formato padrão.
- **Desenvolvimento**: Implementou a validação das datas.
- **Design**: Criou a interface para inserção das datas.
- **QA**: Testou a validação das datas e tratamento de erros.

### Funcionalidade: Campos Dinâmicos com Base no Tipo de Curso
- **PO**: Definiu quais campos adicionais são exibidos por tipo de curso.
- **Desenvolvimento**: Implementou a lógica para campos dinâmicos.
- **Design**: Desenvolveu a interface para exibição de campos adicionais.
- **QA**: Testou a exibição dinâmica dos campos.

### Funcionalidade: Validação do Número de Vagas
- **PO**: Definiu que o número de vagas deve ser um número inteiro positivo.
- **Desenvolvimento**: Implementou a validação do número de vagas.
- **Design**: Criou a interface para inserção do número de vagas.
- **QA**: Testou a validação do número de vagas.

### Funcionalidade: Visualizar Lista de Cursos
- **PO**: Estabeleceu requisitos para exibição da lista, paginação e filtros.
- **Desenvolvimento**: Implementou a visualização, paginação e filtros.
- **Design**: Criou o layout da página de lista de cursos.
- **QA**: Testou a lista de cursos, paginação e filtros.

### Funcionalidade: Atualização em Tempo Real da Lista de Cursos
- **PO**: Definiu a necessidade de atualização em tempo real.
- **Desenvolvimento**: Implementou a atualização em tempo real.
- **Design**: Garantiu que a interface suportasse atualizações.
- **QA**: Testou a atualização em tempo real.

### Funcionalidade: Confirmação Antes de Excluir Curso
- **PO**: Definiu a necessidade de confirmação antes da exclusão.
- **Desenvolvimento**: Implementou a caixa de diálogo de confirmação e lógica de exclusão.
- **Design**: Criou a interface para confirmação da exclusão.
- **QA**: Testou a funcionalidade de confirmação antes da exclusão.
