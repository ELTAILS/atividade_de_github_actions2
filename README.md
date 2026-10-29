🚀 Atividade de GitHub Actions

Este repositório foi desenvolvido por Adrian Arcanjo e Wagner da Silva como parte de uma atividade prática sobre GitHub Actions.

📌 Sobre o projeto

O objetivo é aprender como o GitHub Actions funciona e como ele pode automatizar tarefas dentro de um repositório, facilitando o desenvolvimento e reduzindo processos manuais.

⚙️ O que é GitHub Actions?

O GitHub Actions é uma ferramenta que permite executar tarefas automaticamente quando determinados eventos acontecem no GitHub, como o envio de alterações ao repositório.

Com ele, é possível automatizar testes, verificações e outras etapas do desenvolvimento.

🔄 Como funciona?

De forma simples, o processo acontece assim:

Uma alteração é enviada ao repositório.
Um evento configurado inicia o workflow.
O GitHub executa as etapas definidas.
O resultado fica disponível na aba Actions.

 - name: Gerar CHANGELOG.md
        run: | 01: O uso do pipe é necessário por ter varias linhas.
          echo "# Changelog" > CHANGELOG.md 02: criando um novo arquivo CHANGELOG.md com o nome Changelog.
          echo "" >> CHANGELOG.md 03: escreve uma linha em branco no arquivo.
          git log -20 --pretty=format:"- %s (%an, %ad)" --date=short >> CHANGELOG.md 04: pesquisa os ultimos 20 commits e os adicionam com as mensagens e a data da adição.

      - name: Commitar changelog
        run: | 01: O uso do pipe é necessário por ter varias linhas.
          git config user.name "github-actions[bot]" 02: define um nome para o commit automatico.
          git config user.email "github-actions[bot]@users.noreply.github.com" 03: define o e-mail do usuário automático do GitHub Actions. 
          git add CHANGELOG.md 04: prepara o CHANGELOG.md para ser commitado.
          git diff --staged --quiet || git commit -m "docs: atualiza changelog [skip ci]" 05: vê se foi feita alguma alteração e caso tenha commita com uma msg indicada pelo usuario.
          git push 06: envia o commit para o repositório do GitHub.

🛠️ Tecnologias utilizadas
GitHub
GitHub Actions
YAML
Markdown

👥 Autores
Adrian Arcanjo : 250499
Wagner da Silva : 250270

📚 Referência
Documentação oficial do GitHub Actions
