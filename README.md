# simulado_pf_objetos

1. Estrutura inicial do projeto

[ ] Alterar o nome do projeto no pom.xml
Atualizar artifactId e name, se necessário.


[ ] Alterar o package principal
Ex.: br.edu.insper.sistema_projetos → br.edu.insper.sistema_escolar.


[ ] Renomear a classe Application
Ex.: SistemaProjetosApplication → SistemaEscolarApplication.


[ ] Conferir application.properties
Alterar nome da aplicação, URL do banco H2 e configurações necessárias.




2. Model — Entidades

[ ] Renomear as classes de modelo
Pessoa → Aluno; Projeto → Curso; Departamento → Faculdade.


[ ] Alterar os atributos
Adicionar, remover ou renomear campos conforme o enunciado.


[ ] Manter @Entity e @Id
Conferir @GeneratedValue e os tipos dos IDs.


[ ] Atualizar os relacionamentos
Verificar @ManyToMany, @OneToMany e @ManyToOne.


[ ] Atualizar getters, setters e construtores
Cada atributo novo precisa ser tratado corretamente.


[ ] Evitar referências circulares no JSON
Usar DTOs de resposta ou configurar a serialização das associações.




3. Repository — Banco de dados

[ ] Renomear os Repositories
PessoaRepository → AlunoRepository, por exemplo.


[ ] Alterar JpaRepository
Usar a nova entidade e o tipo correto do ID.


[ ] Atualizar métodos de busca
Ex.: findByCpf → findByMatricula, se necessário.


[ ] Verificar unicidade
Aplicar restrições para CPF, matrícula, e-mail ou outros campos exigidos.




4. DTOs — Dados de entrada e saída

[ ] Renomear os DTOs
Ex.: ProjetoRequest → CursoRequest.


[ ] Alterar os campos dos requests
Os nomes precisam corresponder ao JSON enviado pelo Postman.


[ ] Atualizar as validações
@NotBlank, @NotNull, @Email, @Size, @Positive etc.


[ ] Atualizar os DTOs de resposta
Incluir os atributos e relacionamentos exigidos, sem expor senhas.




5. Service — Regras de negócio

[ ] Renomear os Services
PessoaService → AlunoService, por exemplo.


[ ] Atualizar os tipos e imports
Substituir referências às entidades antigas.


[ ] Adaptar os métodos CRUD
Criar, listar, buscar, atualizar e excluir.


[ ] Adaptar os métodos de relacionamento
Ex.: adicionarAlunoAoCurso e removerAlunoDoCurso.


[ ] Validar entidades relacionadas
Conferir se o curso, aluno ou faculdade existem antes de associar.


[ ] Atualizar mensagens de erro
Ex.: Projeto não encontrado → Curso não encontrado.


[ ] Conferir regras de exclusão
Evitar exclusões que violem relacionamentos ou regras do enunciado.




6. Controller — Endpoints REST

[ ] Renomear os Controllers
ProjetoController → CursoController.


[ ] Alterar @RequestMapping
Ex.: /projetos → /cursos.


[ ] Adaptar @PostMapping, @GetMapping, @PutMapping e @DeleteMapping
Conforme as operações solicitadas.


[ ] Atualizar @PathVariable e @RequestBody
Conferir IDs, DTOs e parâmetros.


[ ] Manter @Valid
Para executar as validações dos DTOs.


[ ] Conferir os códigos HTTP
201 para criação, 200 para consultas, 204 para exclusão sem conteúdo.




7. Autenticação JWT e segurança

[ ] Manter JwtService e JwtAuthenticationFilter
Se a autenticação continuar com o mesmo modelo.


[ ] Atualizar SecurityConfig
Liberar cadastro e login e proteger os novos endpoints.


[ ] Adaptar a entidade Usuario, se necessário
Se o enunciado exigir novos dados de conta ou perfis.


[ ] Conferir PasswordEncoder
Continuar armazenando senhas com hash BCrypt.


[ ] Testar rotas com e sem token
Confirmar respostas 401 e 403 adequadas.




8. Tratamento de erros

[ ] Manter GlobalExceptionHandler
Reaproveitar a estrutura de resposta JSON.


[ ] Adaptar mensagens e exceções
Conforme as novas regras de negócio.


[ ] Verificar erros de validação
Testar campos vazios, IDs inexistentes e dados duplicados.




9. Testes finais no Postman

[ ] Cadastrar um usuário e fazer login
Guardar o JWT recebido.


[ ] Testar os CRUDs
Criar, listar, buscar, atualizar e excluir.


[ ] Testar os relacionamentos
Adicionar e remover entidades relacionadas.


[ ] Testar requisições inválidas
Campos obrigatórios ausentes e IDs inexistentes.


[ ] Reiniciar a aplicação
Verificar se os dados continuam no banco H2 em arquivo.
