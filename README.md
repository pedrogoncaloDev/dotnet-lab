# dotnet-lab

Laboratório para praticar .NET. Cada pasta na raiz é um projeto independente, dedicado a um assunto, e todos ficam na solução `dotnet-lab.slnx`.

## Índice

| Assunto  | O que estudei                                                               | Pasta                |
| -------- | --------------------------------------------------------------------------- | -------------------- |
| Deadlock | Deadlock com `async`/`await` e `.Result` num `SynchronizationContext` de uma thread | [deadlock](deadlock) |
| API      | Projeto inicial, ainda só com o template                                    | [api](api)           |

Ao criar um novo assunto, adicione uma linha nesta tabela.

## Como criar um novo assunto

### Pelo Visual Studio

1. Abra a solução em **Arquivo → Abrir → Projeto/Solução** e escolha `dotnet-lab.slnx`. Se a pasta for aberta no lugar da solução, o menu "Novo Projeto" não aparece.
2. No Gerenciador de Soluções, clique com o botão direito na **solução** `dotnet-lab` e escolha **Adicionar → Novo Projeto…**
3. Escolha o template: **Aplicativo de Console** para um assunto simples ou **ASP.NET Core Web API** para uma API.
4. Defina o **Nome do projeto** com o nome do assunto (por exemplo, `async-await`).
5. Defina o **Local** como a raiz do repositório (`D:\GitHub\dotnet-lab`), sem subpastas no final.
6. Escolha o framework (o `deadlock` usa .NET 9.0 e o `api`, .NET 10.0).
7. Clique em **Criar**.

### Pela linha de comando

Na raiz do repositório:

```bash
dotnet new console -n async-await -o async-await
dotnet sln add async-await/async-await.csproj
```

Troque `console` por `webapi` para criar uma API.

## Como executar um assunto

Cada pasta é um projeto, então cada um roda separado.

### Pelo Visual Studio

1. Clique com o botão direito no projeto e escolha **Definir como Projeto de Inicialização**. O nome fica em negrito.
2. Pressione **Ctrl+F5** para rodar sem depurar ou **F5** para depurar.

Para rodar sem trocar o projeto de inicialização, clique com o botão direito no projeto e escolha **Depurar → Iniciar Nova Instância** (ou **Iniciar Sem Depuração**).

### Pela linha de comando

Na raiz do repositório, aponte para a pasta do assunto:

```bash
dotnet run --project async-await
```

Ou entre na pasta e rode:

```bash
cd async-await
dotnet run
```

Para só compilar tudo, rode `dotnet build` na raiz.

## Convenções

- Um assunto por pasta, cada pasta com o seu projeto.
- Não é preciso numerar as pastas. Use só o nome do assunto, como `async-await` ou `linq`.
- Saídas de build (`bin/`, `obj/`) e arquivos de IDE ficam fora do Git (ver `.gitignore`).
