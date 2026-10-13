# Working Girls — Squad 56 (Recode PRO)

<img width="300px" src="./wwwroot/img/logo-demo.png" alt="Logo Working Girls">

> 📦 **Projeto de estudo — não recebe mais atualizações.**

Projeto social desenvolvido em 2022 pelo **Squad 56** no programa **Recode PRO**. É uma plataforma de anúncios de serviços voltada para mulheres: a usuária se cadastra, faz login e publica anúncios com título, descrição, valor, imagem, cidade e estado.

- Vídeo de demonstração: https://youtu.be/WYIzR51pxD0
- O site chegou a ficar hospedado em http://workinggirls.somee.com/, mas o endereço não responde mais (verificado em outubro de 2026).

## O que tem no repositório

- **Raiz (`Controllers/`, `Models/`, `Views/`, `Areas/Identity/`, `Data/`)**: aplicação ASP.NET Core MVC com login/cadastro via ASP.NET Core Identity (mensagens traduzidas para português) e CRUD de anúncios restrito a usuárias autenticadas.
- **`Data/Migrations/`**: migrations do Entity Framework Core.
- **`script squad56.sql`**: script SQL Server com a criação das tabelas.
- **`frontend-react/`**: versão do front-end em React (páginas Home, Anúncios, Perfil, Contato e Política de Cookies).

## Tecnologias

- C# / ASP.NET Core MVC (.NET 5) + Razor
- ASP.NET Core Identity (autenticação)
- Entity Framework Core 5 + SQL Server
- React 17, React Router 6 (create-react-app)
- Bootstrap, HTML, CSS e JavaScript

## Como abrir / rodar

### Backend (ASP.NET Core MVC)

1. Instale o SDK do .NET 5 (ou um SDK mais novo com o *targeting pack* do .NET 5) e um SQL Server local.
2. Em `appsettings.json`, crie a chave `ConnectionStrings:DefaultConnection` (o `Startup.cs` lê esse nome; no arquivo só existe `DefaultConnectionOld`). Exemplo:
   ```json
   "DefaultConnection": "Server=.;Database=Entrega15_02;Trusted_Connection=True;MultipleActiveResultSets=true"
   ```
3. Crie o banco com as migrations (`dotnet ef database update`) ou executando o `script squad56.sql`.
4. Rode com `dotnet run` (ou abra `ProjetoEntrega15-02.sln` no Visual Studio) e acesse o endereço exibido no terminal.

### Front-end (React)

```bash
cd frontend-react
npm install
npm start
```

O app abre em http://localhost:3000.

> O .NET 5 e o React 17 / react-scripts 5 estão desatualizados. Em um ambiente atual pode ser necessário atualizar o `TargetFramework` e as dependências.
