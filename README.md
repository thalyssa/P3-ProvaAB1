# P3-ProvaAB1

## Funcionalidades

### Adição e remoção de informações:
   A edição de um projeto só pode ser feita pelo coordenador, assim como a criação de um projeto só pode ser feita por um usuário do tipo professor ou pesquisador (Que são automaticamente alocados como coordenadores no momento do registro no sistema). As datas são objetos do tipo GregorianCalendar e devem receber o devido tratamento de exceção para garantir que nenhuma data inválida (Ex.: 31/02) será colocada.
    
### Associação de usuários:
   Um usuário pode ser adicionado no projeto apenas pelo coordenador do mesmo. A função verifica se o usuário existe no sistema e, se existir, o adiciona na lista interna de colaboradores do projeto em questão. Após isso, o ID do projeto é adicionado na lista interna de projetos do usuário alocado, atributo que registra quais projetos o usuário participa.

### Alteração do status:
   A função recebe como parâmetro o status atual do projeto e, com base nele, verifica se é possível passar para o próximo status. Se for possível, a função confirma a identidade do solicitante (que deve ser o coordenador, ou a operaçao não será concluída) e prossegue com o update, caso contrário, uma mensagem de erro é exibida informando os requisitos necessários para a conclusão da alteração.

### Consultas:
   As consultas podem ser solicitados por qualquer usuário do sistema, bastando fornecer o ID do projeto/atvidade ou a matrícula do usuário nas devidas funções (buscarProjeto, buscarAtividade e buscarUsuario, respectivamente). Deve haver tratamento de exceção nessas funções para impedir a aceitação de entradas vazias ou nulas

### Relatório geral da unidade acadêmica:
   O relatório geral da comunidade acadêmica também pode ser solicitado por qualquer usuário do sistema, assim como as consultas. Porém, ao contrário das anteriores, a função para gerar o relatório geral não recebe parâmetros, uma vez que retorna todos os projetos e atividades existentes no banco de dados. Caso não exista nenhum projeto ou atividade registrado, a função exibe uma mensagem informativa para o usuário.
