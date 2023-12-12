# O que é Git e Github?

`Git` um gerenciador de versões que nos permite controlar versões de nossa aplicação durante um determinado tempo. `Github` é uma plataforma que, integrada com o Git, permite que os usuários hospedem seus projetos na internet, permitindo que outros usuários visualizem e consigam contribuir com projetos.

# Comandos Essenciais - Git

## Iniciante

- `init`: inicializa o repositório, criando um diretório oculto .git.
- `status`: descreve todas as alterações realizadas no repositório (local)
- `add`: adiciona arquivos na `staging area`, um meio-termo entre as alterações realizadas entre os arquivos e o que foi feito o commit.
- `commit -m`: adiciona os arquivos presentes na staging area para o repositório local.

## Intermediário

- `restore --stage`: remove os arquivos da staging area.
- `log`: mostra todo o histórico do projeto, demonstrando todos os commits.
- `rm -rf`: remove um arquivo.
- `reset (hash)`: remove todos os commits realizados após o hash específico do commit especificado. Os commits são excluídos e as alterações presentes nesses commits foram transferidas para a staging area.

## Avançado

`stash`: adiciona os arquivos modificados (da staging area) para uma área de stash, que permite que sejam armazenados os arquivos sem fazer um commit, mas também sem o risco de perdê-los.

`stash pop`: remove os arquivos da stash area e os insere novamente na staging area.

`stash clear`: remove os arquivos da stash area e os exclui do fluxo do git.

# Github

## Iniciante

`remote add origin <url>`: adiciona um repositório remoto.

`remote -v`: mostra todas as urls adicionadas na pasta selecionada.

`clone <url>`: baixa uma cópia do projeto localmente do repositório remoto.

`push`: adiciona as alterações locais no repositório especificado.

## Intermediário

- O que são branchs? → Trata-se de uma funcionalidade que nos permite separar o repositório em diferentes partes, sendo cada uma delas representada por uma branch.
- O que é a HEAD? → É um ponteiro que indica onde todas as alterações serão salvas, segundo a branch atual.
- O que é um Fork? É um meio de contribuir com projetos, de forma que o repositório original seja conservado.
- O que é um upstream? É o nome dado a urls provenientes dos repositórios cujo fork é feito.

### Comandos

- `branch`: cria uma nova branch.
- `checkout`: muda a posição do ponteiro HEAD para a branch especificada. Todas as alterações são realizadas na branch espeficificada.

## Avançado

- O que são pull requests? → São requisições feitas por usuários que não possuem as permissões necessárias para diretamente realizar o merge, de forma que o dono do repositório consiga escolher se pode ser inserida uma nova branch (o merge).
- Como remover commits de uma pull request? → Conforme os conceitos aprendidos, poderíamos adicionar o commit para a stage area e depois colocá-lo para a stash, para que assim estes possam ser removidos.
- Como manter sincronizado o número dos commits e as branches de um repositório com a pull request criada? → utilizamos o `git fetch --all --prune`. Isso permitirá que o git local atualize o necessário. Além disso, utilizamos o comando `git reset --hard upstream main`******.****** Por fim, podemos confirmar as mudanças utilizando git push.
- Como fazer o merge de dois ou mais commits? Utilizando `rebase -i`, podemos especificar um hash de um commit e classificar manualmente como pick ou squash (representado por s), onde todos os squashes serão unidos em um único commit e o pick será o ponto de partida dessa união.
- Como resolver merge conflicts? Quando há uma ou mais pessoa resolvendo a mesma linha de código, podemos dizer que o código possui um merge conflict. Para decidir qual das alterações  serão feitas, utilizamos a interface gráfica do github.

# Leitura Complementar - Git e Github

https://towardsdatascience.com/git-help-all-2d0bb0c31483