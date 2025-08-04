<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Portfólio Profissional</title>
    <style>
        /* Paleta de cores moderna e tipografia */
        :root {
            --bg-primary: #f5f5f5;
            --bg-secondary: #ffffff;
            --text-primary: #121212;
            --text-secondary: #555;
            --accent: #007bff;
            --card-bg: #ffffff;
            --card-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            --transition-fast: 0.3s ease;
        }

        body.dark-mode {
            --bg-primary: #121212;
            --bg-secondary: #1e1e1e;
            --text-primary: #e0e0e0;
            --text-secondary: #a0a0a0;
            --accent: #6cace4;
            --card-bg: #1e1e1e;
            --card-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            margin: 0;
            transition: background-color var(--transition-fast), color var(--transition-fast);
        }

        /* Estilo do cabeçalho e navegação */
        header {
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            z-index: 1000;
            background-color: var(--bg-secondary);
            box-shadow: var(--card-shadow);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--text-primary);
            text-decoration: none;
            transition: color var(--transition-fast);
        }

        .nav-links {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            transition: color var(--transition-fast);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background-color: var(--accent);
            bottom: -5px;
            left: 0;
            transition: width var(--transition-fast);
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .theme-toggle, .mobile-menu-btn {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text-primary);
            display: flex;
            align-items: center;
        }

        .mobile-menu-btn {
            display: none;
        }

        /* Estilo da seção principal */
        main {
            padding-top: 70px;
        }

        .section {
            padding: 6rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }

        .section-title h2::after {
            content: '';
            display: block;
            width: 50%;
            height: 4px;
            background-color: var(--accent);
            margin: 10px auto 0;
        }

        /* Seção Hero */
        .hero {
            height: 80vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            /* A imagem de fundo foi removida daqui */
            color: var(--text-primary);
        }

        .hero-content {
            max-width: 800px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
        }

        
            /* Estilo para a parte do texto */
        

        .hero h1 {
            font-size: 3.5rem;
            margin: 0;
            font-weight: 700;
        }

        .hero p {
            font-size: 1.5rem;
            font-weight: 300;
            margin-top: 1rem;
        }

        .hero-btns {
            margin-top: 2rem;
            display: flex;
            justify-content: center;
            gap: 1rem;
        }

        .btn {
            background-color: var(--accent);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s ease, background-color 0.3s ease;
        }

        .btn-outline {
            background: none;
            border: 2px solid var(--accent);
            color: var(--text-primary);
        }

        .btn:hover {
            transform: translateY(-5px);
        }

        .btn-outline:hover {
            background-color: var(--accent);
            color: white;
        }

        /* Seção Sobre Mim */
        .about-content {
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
            font-size: 1.1rem;
        }

        /* Seção Habilidades */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background-color: var(--card-bg);
            padding: 2rem;
            border-radius: 12px;
            box-shadow: var(--card-shadow);
            text-align: center;
            transition: transform var(--transition-fast);
        }

        .skill-card:hover {
            transform: translateY(-10px);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin: 0;
        }

        /* Seção Projetos */
        .project-filters {
            text-align: center;
            margin-bottom: 2rem;
        }

        .filter-btn {
            background: none;
            border: none;
            color: var(--text-secondary);
            font-size: 1rem;
            font-weight: 600;
            padding: 0.5rem 1rem;
            margin: 0 0.5rem;
            cursor: pointer;
            border-radius: 20px;
            transition: background-color var(--transition-fast), color var(--transition-fast);
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--accent);
            color: white;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--card-shadow);
            transition: transform var(--transition-fast);
        }

        .project-card:hover {
            transform: scale(1.03);
        }

        .project-image {
            width: 100%;
            height: 200px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-tags {
            margin-top: 1rem;
        }

        .project-tag {
            background-color: rgba(0, 123, 255, 0.1);
            color: var(--accent);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Seção Contato */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            padding: 2rem;
            background-color: var(--card-bg);
            border-radius: 12px;
            box-shadow: var(--card-shadow);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ccc;
            border-radius: 8px;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            font-family: inherit;
            transition: border-color var(--transition-fast);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent);
        }

        .submit-btn {
            width: 100%;
            padding: 1rem;
            background-color: var(--accent);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 500;
            cursor: pointer;
            transition: background-color var(--transition-fast);
        }

        .submit-btn:hover {
            background-color: #0062be;
        }

        /* Rodapé */
        footer {
            text-align: center;
            padding: 2rem 5%;
            background-color: var(--bg-secondary);
            border-top: 1px solid rgba(0, 0, 0, 0.1);
            margin-top: 2rem;
        }

        .social-links {
            margin-bottom: 1rem;
        }

        .social-links a {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin: 0 0.5rem;
            transition: color var(--transition-fast);
        }

        .social-links a:hover {
            color: var(--accent);
        }

        .copyright {
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        /* Media Queries para responsividade */
        @media (max-width: 768px) {
            .nav-links {
                flex-direction: column;
                position: absolute;
                top: 70px;
                right: 0;
                width: 100%;
                background-color: var(--bg-secondary);
                box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
                transform: translateY(-100%);
                transition: transform var(--transition-fast);
                padding: 1rem 0;
            }

            .nav-links.active {
                transform: translateY(0);
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .skills-container, .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#" class="logo"> Meu Portfólio</a>
            <div class="nav-links">
                <a href="#about">Sobre</a>
                <a href="#skills">Habilidades</a>
                <a href="#projects">Projetos</a>
                <a href="#contact">Contato</a>
                <button class="theme-toggle" id="themeToggle">🌓</button>
            </div>
            <button class="mobile-menu-btn" id="mobileMenuBtn">☰</button>
        </nav>
    </header>

    <main>
        <section class="hero">
            <div class="hero-content">
                <div class="hero-text fade-in">
                    <h1>Olá, eu sou <span style="color: var(--accent);">Romário Lopes</span></h1>
                    <p class="delay-1 fade-in">Desenvolvedor com foco na experiência do usuário, e na interação com o usuário.</p>
                    <div class="hero-btns delay-2 fade-in">
                        <a href="#contact" class="btn">Contato</a>
                        <a href="#projects" class="btn btn-outline">Projetos</a>
                    </div>
                </div>
            </div>
        </section>

        <section id="about" class="section">
            <div class="section-title">
                <h2>Sobre Mim</h2>
            </div>
            <div class="about-content">
                <p>Ainda cursando dev de sistemas mas</p>
                <p>Acredito que tecnologia deve ser acessível, intuitiva e resolver problemas reais.</p>
            </div>
        </section>

        <section id="skills" class="section">
            <div class="section-title">
                <h2>Habilidades</h2>
            </div>
            <div class="skills-container">
                <div class="skill-card">
                    <div class="skill-icon">💻</div>
                    <h3>Front-end</h3>
                    <p>HTML, CSS, JavaScript.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🛢️</div>
                    <h3>Banco de Dados</h3>
                    <p>MySQL, PostgreSQL.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🎨</div>
                    <h3>Design</h3>
                    <p>UI/UX.</p>
                </div>
            </div>
        </section>

        <section id="projects" class="section">
            <div class="section-title">
                <h2>Meus Projetos</h2>
            </div>
            <div class="project-filters">
                <button class="filter-btn active" data-filter="all">Todos</button>
                <button class="filter-btn" data-filter="frontend">Front-end</button>
                <button class="filter-btn" data-filter="backend">Back-end</button>
                <button class="filter-btn" data-filter="mobile">Mobile</button>
            </div>
            <div class="projects-grid">
                <div class="project-card frontend">
                    <div class="project-image">
                        <img src="images/projeto-landing-page.png" alt="Projeto de Landing Page">
                    </div>
                    <div class="project-info">
                        <h3>Landing Page de Evento</h3>
                        <p>Uma landing page responsiva e moderna, criada para promover um evento de tecnologia. Inclui formulário de inscrição e galeria de palestrantes.</p>
                        <div class="project-tags">
                            <span class="project-tag">HTML</span>
                            <span class="project-tag">CSS</span>
                            <span class="project-tag">JavaScript</span>
                        </div>
                    </div>
                </div>

                <div class="project-card backend">
                    <div class="project-image">
                        <img src="images/projeto-api.png" alt="API de E-commerce">
                    </div>
                    <div class="project-info">
                        <h3>API RESTful para E-commerce</h3>
                        <p>Desenvolvimento de uma API completa para um sistema de e-commerce, com rotas para produtos, usuários, carrinho de compras e autenticação.</p>
                        <div class="project-tags">
                            <span class="project-tag">Node.js</span>
                            <span class="project-tag">Express</span>
                            <span class="project-tag">PostgreSQL</span>
                        </div>
                    </div>
                </div>

                <div class="project-card mobile">
                    <div class="project-image">
                        <img src="images/projeto-mobile.png" alt="Aplicativo de Tarefas">
                    </div>
                    <div class="project-info">
                        <h3>Aplicativo de Gestão de Tarefas</h3>
                        <p>Um aplicativo mobile simples para gerenciar tarefas diárias, permitindo adicionar, editar, remover e marcar tarefas como concluídas.</p>
                        <div class="project-tags">
                            <span class="project-tag">React Native</span>
                            <span class="project-tag">JavaScript</span>
                        </div>
                    </div>
                </div>

                <div class="project-card frontend">
                    <div class="project-image">
                        <img src="images/projeto-redesign.png" alt="Redesign de Site">
                    </div>
                    <div class="project-info">
                        <h3>Redesign de Site Institucional</h3>
                        <p>Análise e redesenho de um site existente, com foco na melhoria da usabilidade (UX) e na criação de uma interface mais moderna e intuitiva (UI).</p>
                        <div class="project-tags">
                            <span class="project-tag">UI/UX Design</span>
                            <span class="project-tag">Figma</span>
                            <span class="project-tag">Pesquisa de Usuário</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="section">
            <div class="section-title">
                <h2>Contato</h2>
            </div>
            <div class="contact-form">
                <form action="seu_script_de_contato.php" method="POST">
                    <div class="form-group">
                        <label for="name">Nome</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Mensagem</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Enviar</button>
                </form>
            </div>
        </section>
    </main>

    <footer>
        <div class="social-links">
            <a href="#">🔗</a>
            <a href="#">🔗</a>
            <a href="#">🔗</a>
        </div>
        <div class="copyright">©De Romário Lopes. Todos os direitos reservados.</div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Alternância de Tema
            const themeToggle = document.getElementById('themeToggle');
            const body = document.body;
            const currentTheme = localStorage.getItem('theme');

            if (currentTheme) {
                body.classList.add(currentTheme);
            } else {
                body.classList.add('light-mode');
            }

            themeToggle.addEventListener('click', () => {
                if (body.classList.contains('light-mode')) {
                    body.classList.remove('light-mode');
                    body.classList.add('dark-mode');
                    localStorage.setItem('theme', 'dark-mode');
                } else {
                    body.classList.remove('dark-mode');
                    body.classList.add('light-mode');
                    localStorage.setItem('theme', 'light-mode');
                }
                themeToggle.textContent = body.classList.contains('light-mode') ? '🌓' : '☀️';
            });

            // Menu Responsivo
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const navLinks = document.querySelector('.nav-links');

            mobileMenuBtn.addEventListener('click', () => {
                navLinks.classList.toggle('active');
                mobileMenuBtn.textContent = navLinks.classList.contains('active') ? '✖' : '☰';
            });

            // Filtro de Projetos
            const filterBtns = document.querySelectorAll('.filter-btn');
            const projects = document.querySelectorAll('.projects-grid .project-card');

            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    document.querySelector('.filter-btn.active')?.classList.remove('active');
                    btn.classList.add('active');

                    const filter = btn.dataset.filter;

                    projects.forEach(project => {
                        if (filter === 'all' || project.classList.contains(filter)) {
                            project.style.display = 'block';
                        } else {
                            project.style.display = 'none';
                        }
                    });
                });
            });

            // Rolagem Suave
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
        });
    </script>
</body>
</html>
