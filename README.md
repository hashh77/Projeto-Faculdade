Sistema de Gerenciamento de Clientes e Produtos

🔧 O que o código faz?
É um sistema simples de cadastro de clientes e produtos, com as seguintes funções:

✅ Inserir clientes
✅ Inserir produtos
✅ Listar clientes
✅ Excluir clientes
✅ Atualizar clientes

O sistema funciona por meio de um menu interativo no terminal.

🗂️ Declarações globais

char clientes[10][50];
char produtos[10][50];
int total_clientes = 0;
int total_produtos = 0;

clientes[10][50]: Vetor para até 10 clientes, cada um com no máximo 49 caracteres (mais o \0 de fim de string).
produtos[10][50]: Mesmo conceito, para produtos.
total_clientes e total_produtos: Contadores que dizem quantos clientes ou produtos já foram cadastrados.

🔸 Função insere_cliente()

Verifica se há espaço (até 10 clientes).
Solicita um nome ao usuário.
Usa scanf("%s", ...) para ler o nome (atenção: lê apenas até o primeiro espaço).
Incrementa o contador total_clientes.

🔸 Função insere_produto()
Funciona da mesma forma que insere_cliente(), mas para produtos.

🔸 Função lista_cliente()

Percorre o vetor clientes.
Imprime cada cliente na tela com numeração (começando em 1).

🔸 Função exclui_cliente()

Pede ao usuário o número do cliente a ser removido (de 1 até total_clientes).
Valida se o número é válido.
Desloca todos os clientes após o índice escolhido uma posição para trás, sobrescrevendo quem será excluído:

for(int i = indice; i < total_clientes - 1; i++) {
    strcpy(clientes[i], clientes[i + 1]);
}

Decrementa o contador total_clientes.
Exibe mensagem de sucesso.

🔸 Função atualiza_cliente()

Pede o número do cliente a ser atualizado.
Verifica se o número é válido.
Solicita o novo nome e atualiza diretamente no vetor clientes.

🔸 Função main()
Contém um loop com menu interativo, que oferece as opções:

0 - Sair
1 - Inserir Cliente
2 - Inserir Produto
3 - Listar clientes
4 - Excluir cliente
5 - Atualizar cliente

Dependendo da escolha do usuário, chama a função correspondente.
O loop repete até o usuário digitar 0 (para sair).


⚠️ Pontos de atenção e melhorias

📛 O uso de scanf("%s", ...) não lê nomes com espaços (ex.: "João Silva" vai ler só "João").
✔️ Melhor usar fgets().
📦 Os produtos são inseridos, mas não existe função para listar, excluir ou atualizar produtos.
💾 Tudo está na memória; ao encerrar, os dados são perdidos. Poderia ter leitura/escrita em arquivos.
📏 Limitações fixas: no máximo 10 clientes e 10 produtos.

