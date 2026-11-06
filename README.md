# dotnet-lab

Laboratório para praticar .NET. Cada pasta na raiz é um projeto independente, dedicado a um assunto, e todos ficam na solução `dotnet-lab.slnx`.

## Como criar um novo assunto

### Pelo Visual Studio

1. Abra a solução em **Arquivo → Abrir → Projeto/Solução** e escolha `dotnet-lab.slnx`. Se a pasta for aberta no lugar da solução, o menu "Novo Projeto" não aparece.
2. No Gerenciador de Soluções, clique com o botão direito na **solução** `dotnet-lab` e escolha **Adicionar → Novo Projeto…**
3. Escolha o template: **Aplicativo de Console** para um assunto simples ou **ASP.NET Core Web API** para uma API.
4. Defina o **Nome do projeto** como `NN-nome-do-assunto` (por exemplo, `02-async-await`).
5. Defina o **Local** como a raiz do repositório (`D:\GitHub\dotnet-lab`), sem subpastas no final.
6. Escolha **.NET 9.0** como framework, o mesmo do `01-deadlock`.
7. Clique em **Criar**.

### Pela linha de comando

Na raiz do repositório:

```bash
dotnet new console -n 02-nome-do-assunto -o 02-nome-do-assunto
dotnet sln add 02-nome-do-assunto/02-nome-do-assunto.csproj
```

Troque `console` por `webapi` para criar uma API. Se o projeto novo vier com outro framework, ajuste o `TargetFramework` no `.csproj` para `net9.0`.

## Como executar um assunto

No Visual Studio, clique com o botão direito no projeto, escolha **Definir como Projeto de Inicialização** e pressione **Ctrl+F5** (sem depurar) ou **F5** (depurando).

Pela linha de comando:

```bash
dotnet run --project 02-nome-do-assunto
```

## Convenções

- Pastas numeradas em ordem de criação: `01-deadlock`, `02-...`, `03-...`.
- Um assunto por pasta.
- Saídas de build (`bin/`, `obj/`) e arquivos de IDE ficam fora do Git (ver `.gitignore`).
