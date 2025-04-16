🔴 1. Violação do SRP (Princípio da Responsabilidade Única)
Classe: GerenciadorBiblioteca
Métodos: AdicionarUsuario, RealizarEmprestimo, RealizarDevolucao
Problema: A classe faz muitas coisas — gerencia livros, usuários, empréstimos e até envia e-mails/SMS.
Justificativa: Viola o SRP, dificultando manutenção e testes.
Solução: Separar responsabilidades, criando classes como ServicoDeNotificacao, GerenciadorDeUsuarios, GerenciadorDeEmprestimos.

🔴 2. Violação do OCP (Princípio Aberto/Fechado)
Classe: GerenciadorBiblioteca
Método: EnviarEmail, EnviarSMS chamados diretamente
Problema: Se for necessário adicionar WhatsApp ou outro canal, terá que modificar essa classe.
Justificativa: O código deveria ser aberto para extensão, fechado para modificação.
Solução: Criar uma interface INotificador e implementar classes concretas para e-mail, SMS etc.

🔴 3. Violação do DIP (Princípio da Inversão de Dependência)
Classe: GerenciadorBiblioteca
Problema: Depende diretamente de implementações concretas (ex: Console.WriteLine, métodos de notificação).
Justificativa: Isso torna o código menos testável e acoplado.
Solução: Injetar dependências por meio de interfaces.

🔴 4. Código com nomes pouco descritivos
Classe: GerenciadorBiblioteca
Método: AdicionarLivro → variável l, AdicionarUsuario → variável u
Problema: Variáveis de nomes como l e u dificultam a legibilidade.
Justificativa: Viola Clean Code — nomes devem ser significativos.
Solução: Use livro, usuario, etc.

🔴 5. Métodos fazendo muitas coisas ao mesmo tempo
Classe: RealizarEmprestimo, RealizarDevolucao
Problema: Cada método faz lógica de negócio, manipula estado e envia notificações.
Justificativa: Métodos grandes são difíceis de testar e manter.
Solução: Extrair responsabilidades em métodos e classes separados.
