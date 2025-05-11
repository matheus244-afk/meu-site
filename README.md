<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Meu Repositório no GitHub</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Bem-vindo ao meu Repositório!</h1>
        <p>Aqui você encontra meus principais projetos.</p>
    </header>

    <section class="sobre">
        <h2>Sobre Mim</h2>
        <p>Olá! Sou um desenvolvedor apaixonado por tecnologia e inovação. Atualmente estudo Engenharia de Software e busco crescer na área de desenvolvimento de sistemas e automação.</p>
    </section>

    <section class="repositorios">
        <h2>Repositórios no GitHub</h2>
        <div id="repos-container">
            <p>Carregando repositórios...</p>
        </div>
    </section>

    <section class="contato">
        <h2>Contato</h2>
        <p>Você pode entrar em contato comigo pelo e-mail: <strong> moliveira3052@gmail.com</strong></p>
        <p>Ou me seguir no <a href="https://github.com/seu-usuario" target="_blank">GitHub</a>.</p>
    </section>

    <footer>
        <p>© 2025 - Desenvolvido por matheus oliveira</p>
    </footer>

    <script>
        const username = "seu-usuario"; // 🔁 Substitua pelo seu nome de usuário do GitHub
        fetch(https://api.github.com/users/${username}/repos)
            .then(response => response.json())
            .then(data => {
                const container = document.getElementById("repos-container");
                container.innerHTML = "";
                data.forEach(repo => {
                    const div = document.createElement("div");
                    div.className = "repositorio";
                    div.innerHTML = `
                        <h3><a href="${repo.html_url}" target="_blank">📁 ${repo.name}</a></h3>
                        <p>${repo.description || "Sem descrição."}</p>
                    `;
                    container.appendChild(div);
                });
            })
            .catch(error => {
                document.getElementById("repos-container").innerHTML = "<p>Erro ao carregar repositórios.</p>";
            });
    </script>
</body>
</html>
