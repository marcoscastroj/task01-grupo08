# task01-grupo08
## Parte 2

## Git Rebase
<p>O Git Rebase é um comando que te permite combinar/integrar as alterações de uma branch para outra reaplicando os commits.</p>

<p>Sintaxe</p>

```bash
git rebase <branch-alvo>

# Aplicação
git checkout minha-feature
git rebase main
```
<p>Fontes de pesquisa : Atlassian, ChatGPT, IA do google(na barra de pesquisa)</p>

## git cherry-pick

### Funcionamento:

<p>Quando você faz um cherry-pick, o Git pega o commit específico de uma branch e tenta aplicá-lo na branch onde você está no momento, criando um novo commit com a mesma alteração, mas com um novo ID de commit.</p>

<p>Isso pode ser útil quando você quer aplicar uma mudança específica de uma branch (como uma correção ou funcionalidade) sem trazer todo o histórico de commits da branch.</p>

## Sintaxe:

```bash
git cherry-pick <commit-hash>
```
<p>Onde: "commit-hash" é o ID do commit (um identificador único de cada commit) que você quer aplicar. O hash é uma sequência de caracteres que você pode obter com o comando git log.</p>

## Aplicação:

<p><strong>Passo 1:</strong> Identifique o commit que você deseja aplicar.</p>
<p>Suponha que você tem duas branches: develop e feature, e você quer pegar um commit específico da branch feature para aplicar na branch develop.</p>

```bash
git git checkout feature
git log
```

<p>Isso vai te mostrar uma lista de commits, como:</p>

```bash
git commit abc1234 (HEAD -> feature)
Author: Seu Nome <seunome@example.com>
Date:   Thu Mar 25 10:00:00 2025 -0300

    Correção de bug no sistema de login
```

<p>Aqui, o commit com o hash abc1234 é o que você quer aplicar na branch develop.</p>
<br>
<p><strong>Passo 2:</strong> Mude para a branch de destino onde você quer aplicar o commit.</p>
<p>Neste caso, você quer aplicar o commit na branch develop:</p>

```bash
git git checkout develop
```

<p> <strong>Passo 3:</strong> Use o git cherry-pick para aplicar o commit. <br>
Agora, você vai usar o git cherry-pick para aplicar o commit da branch feature na branch develop: </p>

```bash
git git cherry-pick abc1234
```

<p> Isso vai aplicar o commit abc1234 na sua branch develop, criando um novo commit com as mesmas alterações, mas com um ID diferente.</p>

<p><strong>Passo 4:</strong> Resolva conflitos (se houver).</p>
<p>Se houver conflitos de merge, o Git vai pedir para você resolver esses conflitos antes de finalizar o cherry-pick.</p>

<p>Resolva os conflitos nos arquivos.</p>

<p>Depois de resolver os conflitos, marque os arquivos como resolvidos:</p>

```bash
git git add .
```

<p>Complete o cherry-pick com um commit:</p>

```bash
git git cherry-pick --continue
```