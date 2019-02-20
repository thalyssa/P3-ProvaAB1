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

## Classes

### projeto
   Classe que representa a estrutura básica de um projeto e garante os métodos para manipulá-lo. Na variável coordenador, é armazenada a matrícula do usuário criador do projeto, enquanto na ArrayList de colaboradores, são armazenadas as matrículas de todos os acadêmicos envolvidos. A centralização de informações facilita a pesquisa e extração de dados, porém, como os identificadores dos projetos também são armazenados nas ArrayLists internas de cada usuário participante, existe certa redundância de dados.

### atividade
   Classe que registra as atividades partes de um projeto. Toda tarefa é criada como incompleta por padrão (boolean = false) e possui apenas um método: Concluir, que só pode ser chamado pelo usuário cuja matrícula estiver registrada como responsável. O método concluir verifica se todas as subtarefas (ArrayList de atividades) estão finalizadas  e só então marca a atividade principal como concluída (boolean = true).

### user
   Classe-mãe de todas as classes que representam os sub-tipos de usuário possíveis de existir no sistema, além do usuário comum que não necessariamente está vinculado a um projeto acadêmico, como o administrador do sistema. O usuário padrão é capaz de executar buscas por meio dos métodos disponíveis e gerar o relatório geral de projetos e atividades.
