# github-esi
# Atividade Prática 03
>
> [Universidade Federal do Ceará (UFC)](https://www.ufc.br/)\
> [Departamento de Computação (DC)](https://dc.ufc.br/pt/)\
> Disciplina: Engenharia de Sistemas Inteligentes (CK0444 – 2026.2)\
> Professor: [Lincoln S. Rocha](http://lattes.cnpq.br/0656977742590515)\
> E-mail: <lincoln@dc.ufc.br>
>

Prática de Controle de Versão Colaborativo com [GitHub](https://github.com/)

Objetivos da prática:

- Criar e gerenciar repositórios remotos no GitHub.  
- Fixar comandos básicos de Git (ex. `clone`, `add`, `commit`, `push` e `pull`).  
- Usar branches, pull requests e code review na plataforma GitHub.  
- Resolver conflitos de merge e criar tags/releases.

## 1. Pré-quequisitos

### 1.1. Verificando Git

Verifique se o Git está instalado no seu terminal de comandos (`shell` ou `console`).

```bash
git --version
```

### 1.2. Instalando Git

Caso o Git não esteja instalado, vá ao site do [Git](https://git-scm.com/install/) escolha a versão compatível com o seu Sistema Operacional, faça o downlaod e, em seguida, realize a instalação como recomendado no site do Git.

### 1.3. Perfil no GitHub

É necessário possuir uma conta ativa no GitHub. Para isso vá até o site do GitHub na seção reservada a [criação de contas](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).

### 1.4. GitHub Desktop (opcional)

Recomendamos a instação do [GitHub Desktop](https://github.com/apps/desktop?locale=pt-BR) na máquina local para facilitar o processo de autenticação.

### 1.5. Visual Studio Code (VS Code)

Recomendamos o uso da IDE [Visial Studio Code](https://code.visualstudio.com/) para execução desta prática.

## 2. Roteiro da Prática

### 2.1. Criando Repositório no GitHub

Passos para criação do repositório remoto no GitHub:

1. Acesse o [GitHub](https://github.com/) e faça login.  
2. Clique em **New repository**.
3. Preencha:
   - **Repository name:** `github-esi`
   - **Description (opcional):** “Repositório para prática de GitHub em sala de aula”
   - **Visibility:** Public  
4. Marque **Initialize this repository with a README**.  
5. Clique em **Create repository**.

### 2.2. Clonando o Repositório Remoto

Para clocar o repositório remoto execute o comando `clone`:

```bash
git clone https://github.com/SEU_USUARIO_GITHUB/github-esi.git
```
>
> Nota! Antes de fazer o `clone` do repositório, use o terminal para selecionar o diretório para onde o repositório `github-esi` será clonado.
>

### 2.2. Configurando Usuário e E-mail

É interessante que usemos uma configuração padrão para garantir rastreabilidade entre a autoria dos commits feitos localmente com os registrados no repositório remoto. Portanto, usaremos a seguinte sequencia de instruções:

- Vá para dentro diretório do repositório clonado:

```bash
cd github-esi
```

- Altere seu `user.name`

```bash
git config user.name "Seu Nome igual ao GitHub"
```

- Altere seu `user.email`

```bash
git config user.email seu.email@igual.do.github
```

### 2.3. Criando o módulo Python `calac.py`

Usando VS Code, abra a pasta do diretório do repositório (`github-esi`) e crie o arquivo `calc.py` e escreva o seguite trecho código detro dele e salve:

```python
def sub(x, y): 
    return x - y

def mult(x, y): 
    return x * y

def div(x, y):
    return x / y
```

### 2.4. Registrando Primeiras Alterações de `calc.py`

Você agora vai registrar as alterações no repositório usando o comando ``commit`` via VS Code:

- Você deve adicionar as mudanças de `calc.py` em `stage` indo à tela similar a descrita na figura abaixo:

![Adicionando mudanças em stage.](./img/stage.png "Adicionando mudanças em stage.")

- Em seguda, você deve informar a mensagem de commit (`"Primeira versão da calculadora."`) e realizar o `commit` usando a tela similar a da figura abaixo:

![Realizando commit.](./img/commit.png "Realizando commit.")

### 2.5. Enviando Alterações para Repositório Remoto

Você deve fazer o `sync` (`pull` + `push`) indo à tela similar a descrita na figura abaixo:

![Realizando push.](./img/push.png "Realizando push.")

### 2.6. Verificando no GitHub

No navegador, atualize a página do repositório e confirme que `calc.py` apareceu com o conteúdo esperado.

### 2.7. Criando e Trabalhando em uma _feature branch_

Você deve criar a ramificação o `feature/sum` indo à tela similar a descrita na figura abaixo:

![Criando branch.](./img/branch_2.png "Criando branch.")

Agora, selecione a ramificação `feature/sum`. Depois, edite o arquivo `calc.py` para ficar com conteúdo similar ao descrito abaixo:

```python
def sum(x, y):
  return x + y

def sub(x, y): 
    return x - y

def mult(x, y): 
    return x * y

def div(x, y):
    return x / y
```

Em seguida, realize procedimento similar ao descrito em `2.4`, porém com a mensagem de commit igual a `"Adicionando a função sum() na calculadora"`. Após isso, envie a alteração para o repositório remoto seguindo a instrução descrita em `2.5`.

## 2.8. Abrindo um Pull Request (PR)

1. No GitHub, vá em **Pull requests** → **New pull request**.  
2. Selecione base `main` e compare `feature/sum`.  
3. Preencha título: “Feature: soma” e descrição sucinta.  
4. Clique em **Create pull request**.

## 2.9. Revisão de Código e Merge via Interface

- Simule uma revisão de código: comente no PR, peça ajustes (ou aprove de imediato).  
- Depois de aprovado, clique em **Merge pull request** → **Confirm merge**.  
- Traga alterações para o repositório local usando `sync` (imagem descrita no passo `2.5`)
  
## 2.10. Criando uma Issue de Bug

1. No GitHub, vá em **Issues** → **New issue**.  
2. Título: “Divisão por zero causa erro”  
3. Descreva: “Ao chamar `div(10, 0)`, a aplicação lança exceção. Deve retornar `None`.”  
4. Abra a issue.

---

## 2.11. Corrigindo o Bug em _hotfix branch_

Cire o ramo `hotfix/div0` com procedimento similar ao descrito no passo `2.7`. Em seguida, selecione o ramo criado e altere a função `div` de `calc.py`:

```python
  def div(x, y):
      return x / y if y != 0 else None
```

Após isso, registre as alterações conforme descrito em `2.4` usando a seguinte mensagem de `commit`: `"Hotfix: trata divisão por zero"`.

Por fim, envie as alterações do ramo `hotfix/div0` para o repositório remoto (procedimento similar ao realizado no passo `2.5`)

## 2.12. Novo Pull Request para Hotfix

- Crie uma PR de `hotfix/div0` → `main` (similar ao passo `2.8`)
- Associe essa PR com a issue relacionada (veja como fazer isso [aqui](https://docs.github.com/pt/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue))
- Após revisão, **Merge**.

## 2.13. Criando uma Release

- Veja a documentação de como gerenciar releases em repositórios do GitHub [aqui](https://docs.github.com/pt/repositories/releasing-projects-on-github/managing-releases-in-a-repository)
- Crie uma tag com o seguinte nome `0.1.0`.
- Associe essa tag com as notas de release. Lembre-se, a release deve estar associada com a branch principal.
- Dê o seguinte título: `Primeira Versão de Calc`.
- Descreva as quatro oerações fornecidas calculadora no campo de texto.
- Publique a release.

### 2.14. Entrega da Tarefa

Agora você deve enviar via SIGAA o link do repositório remoto (``https://github.com/SEU_USUARIO_GITHUB/github-esi``) como reposta desta tarefa. OBS. A análise do log do repositório será utilizado para verificar a realização correta da tarefa.
