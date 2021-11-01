GitHub - O Guia de Comandos

- Ajuda

  ```jsx
  git help 
  ```

- Ajuda específica

  ```jsx
  git help add
  git help commit
  git help <qualquer_comando_git>
  ```

- Defina o nome de usuário e e-mail

  ```jsx
  git config --global [user.name](<http://user.name/>) "nome do usuario"
  git config --global user.email [email@email.com](<mailto:email@email.com>)
  ```

- Exclua todos os registros que se referem ao usuário e ao e-mail

  ```jsx
  git config --global --unset [user.name](<http://user.name/>) "nome do usuario"
  git config --global --unset user.email [email@email.com](<mailto:email@email.com>)
  ```

- Ver configuração do Git

  ```jsx
   git config --list
  ```

- Crie um novo repositório

  ```jsx
  git init
  ```

- Verifique o status dos arquivos/diretórios

  ```jsx
  git status // mostra o status dos arquivos em seu repositório
  ```

- Adicione um arquivo

  ```jsx
  git add nome_arquivo_diretorio // arquivo específico
  git add . 
  git add --all
  ```

- Confirme um arquivo/diretório

  ```jsx
  git commit nome_arquivo -m "enviar mensagem"
  ```

- Remova um arquivo ou diretório

  ```jsx
  git rm arquivo
  git rm -r diretorio // remove o diretório e os arquivos que ele contém
  ```

- Confirme um arquivo/diretório

  ```jsx
  git commit nome_arquivo -m "enviar mensagem"
  ```

- Veja o histórico de atividades

  ```jsx
  git log // mostra o histórico
  git log -- <histórico do arquivo> // mostra o histórico de um arquivo específico
  git log --author=usuario // mostra o histórico de um determinado usuário
  ```

- Desfazendo a mudança local em seu diretório de trabalho local

  ```jsx
  git checkout -- arquivo // só deve ser usado enquanto o arquivo ainda não foi adicionado ao espaço de trabalho temporário
  ```

- Desfazendo mudança local na área de trabalho temporária

  ```jsx
  git reset HEAD arquivo // deve ser usado quando o arquivo já foi adicionado na área temporária) “Unstaged changes after reset:M arquivo” (se a seguinte saída for exibida, o comando de redefinição não alterou o diretório de trabalho)
  
  git checkout nome_arquivo // permite que você mude o diretório
  ```

- Veja os repositórios remotos (para saber para onde as alterações são enviadas ou de onde as baixamo

  ```jsx
  git remote
  git remote -v
  git remote add origin [git@github.com](<mailto:git@github.com>):meunome/arquivo-git.git // vincula o repositório local a um repositório remoto
  git remote show origin // permite que você veja informações de repositórios remotos
  git remote rename origin nome_novo // renomeia um repositório remoto
  git remote rm nome_git // desvincula um repositório remoto
  git push -u origin main // o envio para o repositório deve conter seu nome e branch
  ```

- Atualize o repositório local com base no repositório remoto

  ```jsx
  git pull // atualiza arquivos em relação à branch atual
  git fetch // obter as alterações, mas não aplicá-las à branch atual
  ```

- Clone um repositório remoto existente

  ```jsx
  git clone [git@github.com](<mailto:git@github.com>):meunome/arquivo-git.git
  ```

- Branches

  - A main (anteriormente, chamada de master) é a branch principal do Git.
  - O HEAD é um ponteiro especial que indica qual é o branch atual. Por padrão, HEAD aponta para a branch principal, o main.

  ```jsx
  git branch nova_branch_nome // cria uma nova branch
  git checkout nova_branch_nome // mudar para uma branch existente - Neste caso, o ponteiro HEAD principal está apontando para a branch nova_branch_nome.
  git checkout -b nova_branch_nome // crie uma nova branch e aponte para ela
  git checkout main // volta para a branch principal main
  git merge nova_branch_nome // resolve a união (merge) entre as branches - Para mesclar, você deve estar na branch que deve receber as alterações.
  git branch -d nova_branch_nome // apagando uma branch
  git branch // lista branches
  git branch -v // lista branches com informações dos últimos commits
  git branch --merged // lista branches que já estão unidas (merged) com a main
  git branch --no-merged // lista branches que não estão unidas (merged) com a main
  git pull origin nomeBranch // extrai arquivos de uma branch existente
  git push origin nova_branch_nome // cria uma branch remota com o mesmo nome
  git merge --abort o git reset --merge // quando temos problema com a união (merge) e queremos desfazê-lo)
  git reset HEAD // quando queremos voltar a um commit anterior. Se quisermos voltar a mais de um commit, devemos colocar o número de commits após HEAD. Exemplo: HEAD~2)
  ```

- Reescrevendo o histórico

  ```jsx
  git commit --amend -m "Minha nova mensagem" // alterar mensagens de confirmação
  ```

