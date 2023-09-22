# Teste Suporte Técnico

## Descrição

Cenário:
- Uma empresa solicitou um sistema simples de compra. Nesse sistema o cliente pode fazer compras em algumas empresas de acordo com os produtos que as mesmas têm disponível em estoque, além disso ele também pode ver as suas compras. Por sua vez, a empresa pode ver as suas vendas e os seus produtos.

As regras de negócios são:

- Cada empresa tem sua taxa (comissão do sistema) para as transações
- Além do administrador e a própria empresa, nenhum outro usuário poderá ver
- informações da empresa (além do nome)
- Ao finalizar uma compra o cliente deve ver um resumo da mesma
- O saldo da empresa deve ser alterado já refletindo as taxas
- A empresa deve vender apenas produtos que ela esteja relacionada
- A empresa poderá ver a taxa de comissão de sistema em cada venda (ao listar
suas vendas)

Teste

- Os erros podem ser desde código, estrutura de dados, boas práticas, experiência do usuário e regras de negócio.
- Descreva como se estivesse repassando os ajustes para um programador.
- Em caso de erros na regra de negócio, faça um relato para a empresa que solicitou o sistema, neste relato deve ser informado o erro e porquê acontece o erro.
- Faça o máximo de ajustes no código, de forma que as falhas sejam corrigidas. Siga a seguinte ordem para ajuste: Regra de negócio, código, boas práticas, estrutura de dados e experiência do usuário.

## Descrição dos erros

Falta de Restrição de Acesso as informações das Empresas pelo admin:
- O código não implementava ações para o admin visualizar dados das empresas e não havia restrição de acesso.

Alteração do Saldo da Empresa:
- O código não atualizava o saldo da empresa corretamente, assim não refletia as taxas de comissão do sistema. Pois após criar a venda, não era atualizado o saldo da empresa subtraindo a comissão do sistema do total da venda.


Validação de Produtos da Empresa:
- O código não impedia a compra de produtos de outras empresas a partir da empresa selecionada, pois não havia um filtro para relacionar cada produto com a espresa em questão. Antes de adicionar um produto ao carrinho, foi necessário verificar se o produto à ser comprado era realmente um produto da empresa selecionada.

Outros erros:
- Código não possuia break no switch case (Main.java), com isso poderia ocorrer erros como: executar outros cases, sair do menu a cada iteração.

- Código Deslogava sempre que executava alguma ação, como finalizar compra. Foi necessário adiciona loop While(true) para cada menu, assim o programa não é encerrado.

- Menu de admin igual ao do cliente. Foi necessário implementar menu para o admin.

- Refatoração dos métodos. Separação de funções que estavam dentro do switch case em métodos, para melhorar visualização, manutenção e legibilidadee do código.

- Ajustes em alguns métodos da classe Usário, para manter padrão no código (isAdmin, isEmpresa, isCliente).
