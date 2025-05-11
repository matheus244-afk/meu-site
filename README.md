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
        <p>Você pode entrar em contato comigo pelo e-mail: <strong>seu.email@exemplo.com</strong></p>
        <p>Ou me seguir no <a href="https://github.com/seu-usuario" target="_blank">GitHub</a>.</p>
    </section>

    <footer>
        <p>© 2025 - Desenvolvido por Seu Nome</p>
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
body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f4f4f4;
    color: #333;
}

header {
    background-color: #24292e;
    color: white;
    padding: 20px;
    text-align: center;
}

section {
    padding: 20px;
    max-width: 900px;
    margin: auto;
}

.repositorio {
    background: white;
    margin-bottom: 20px;
    padding: 15px;
    border-radius: 5px;
    box-shadow: 0 0 5px rgba(0,0,0,0.1);
}

.repositorio a {
    color: #0366d6;
    text-decoration: none;
}

footer {
    background-color: #eee;
    text-align: center;
    padding: 10px;
    margin-top: 40px;
}

.sobre, .contato {
    background-color: #fff;
    margin-bottom: 20px;
    border-radius: 5px;
    box-shadow: 0 0 5px rgba(0,0,0,0.1);
    padding: 15px;
}
