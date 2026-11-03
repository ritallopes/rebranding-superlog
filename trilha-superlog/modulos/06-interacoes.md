# Módulo 6 — Interações e acessibilidade

**Pré-requisito:** módulo 5. **Objetivo:** conectar ações da pessoa à interface.

## Exercício 6.1 — Primeiro evento

**Tarefa:** crie `js/script.js` e conecte com `defer`. Selecione um botão de demonstração com `querySelector` e responda a um clique com `addEventListener`.

**Passos:** altere o texto de uma mensagem usando `textContent`; confira se o seletor corresponde ao HTML; remova o botão de demonstração depois do estudo.

**Confira:** a mensagem muda com clique e ativação pelo teclado; não há erros no console.

## Exercício 6.2 — Menu móvel

**Tarefa:** adicione um botão de menu com `aria-controls` apontando para a navegação e `aria-expanded` indicando o estado.

**Passos:** use o exemplo de apoio; sincronize visibilidade e estado; ao pressionar Escape, feche o menu e devolva o foco ao botão; ao voltar para tela larga, mantenha a navegação visível. Garanta que, sem JavaScript, os links apareçam.

**Confira:** links escondidos não recebem foco; o botão continua acessível; abrir e fechar repetidamente não quebra o menu. Não é necessário usar `role="menu"` em uma navegação comum.

## Exercício 6.3 — Perguntas frequentes

**Tarefa:** refine os elementos `details` e `summary` já criados.

**Passos:** adicione foco visível, espaçamento e indicação de abertura; teste abrir mais de uma pergunta; mantenha o comportamento nativo enquanto ele atende à tarefa.

**Confira:** todas as respostas estão disponíveis com teclado e o estado aberto é perceptível. Escreva por que essa interação dispensa JavaScript adicional.

## Exercício 6.4 — Formulário de demonstração

**Tarefa:** trate `submit`, impeça o envio com `preventDefault` e valide campos obrigatórios e e-mail.

**Passos:** aproveite a validação nativa; adicione mensagens específicas se necessário; preserve os dados quando houver erro; mostre “Demonstração concluída. Nenhuma mensagem foi enviada.” em uma região com `role="status"`.

**Confira:** dados inválidos não geram mensagem de sucesso; a interface nunca afirma que enviou algo; não há requisição nem salvamento de dados pessoais.

## Exercício 6.5 — Preferência local

**Tarefa:** permita escolher texto padrão ou ampliado e persistir somente essa preferência em `localStorage`.

**Passos:** leia a preferência na abertura; aplique uma classe; trate falhas de armazenamento com `try...catch`; mantenha a página utilizável se o armazenamento estiver indisponível.

**Confira:** recarregar preserva a escolha quando permitido e o layout continua funcionando. O recurso complementa o zoom do navegador.

**Entrega:** menu e formulário demonstrativo funcionais, navegação por teclado e preferência local.
