<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website Design Selling</title>
    <style>
        /* Basic styling for layout */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

   header {
            background-color: #333;
            color: white;
            padding: 1rem 0;
            text-align: center;
        }

   nav ul {
            list-style: none;
            padding: 0;
        }

  nav ul li {
            display: inline;
            margin: 0 1rem;
        }

   nav ul li a {
      color: white;
       text-decoration: none;
        }

   #hero {
            background: url('hero-bg.jpg') no-repeat center center/cover;
            color: white;
            padding: 5rem 0;
            text-align: center;
        }

   .designs-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            padding: 2rem 0;
        }

  .designs-container div {
            background-color: #f4f4f4;
            border: 1px solid #ddd;
            margin: 1rem;
            padding: 1rem;
            width: 30%;
            transition: transform 0.3s ease;
        }
    .designs-container div:hover {
            transform: scale(1.05);
        }
     footer {
            background-color: #333;
            color: white;
            padding: 2rem 0;
            text-align: center;
        }
       form {
            max-width: 600px;
            margin: 0 auto;
        }
     form label {
            display: block;
            margin: 1rem 0 0.5rem;
        }

   form input, form textarea {
            width: 100%;
            padding: 0.5rem;
            margin-bottom: 1rem;
        }

  form button {
            background-color: #5cb85c;
            border: none;
            color: white;
            padding: 1rem 2rem;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#hero">Home</a></li>
                <li><a href="#ai-designs">AI Designs</a></li>
                <li><a href="#tech-designs">Tech Designs</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

  <main>
        <section id="hero">
            <h1>Welcome to Fun Website Designs!</h1>
            <p>Find the best website designs for AI and tech companies.</p>
        </section>
     <section id="ai-designs">
            <h2>AI Company Designs</h2>
            <div class="designs-container" id="ai-designs-container"></div>
        </section>
     <section id="tech-designs">
            <h2>Tech Company Designs</h2>
            <div class="designs-container" id="tech-designs-container"></div>
        </section>
    </main>
   <footer id="contact">
        <h2>Contact Us</h2>
        <form id="contact-form">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <label for="message">Message:</label>
            <textarea id="message" name="message" required></textarea>
            <button type="submit">Send</button>
        </form>
    </footer>

   <script>
        // Navigation bar interactivity
        document.querySelectorAll('nav ul li a').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(link.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Dynamic content loading for AI and Tech sections
        const aiDesigns = [
            { title: 'AI Design 1', description: 'A sleek design perfect for AI startups.' },
            { title: 'AI Design 2', description: 'Modern and dynamic AI company template.' },
            { title: 'AI Design 3', description: 'Professional design for AI enterprises.' }
        ];

        const techDesigns = [
            { title: 'Tech Design 1', description: 'Innovative tech company design.' },
            { title: 'Tech Design 2', description: 'Cutting-edge tech startup template.' },
            { title: 'Tech Design 3', description: 'High-tech professional design.' }
        ];

        function loadDesigns(designs, containerId) {
            const container = document.getElementById(containerId);
            designs.forEach(design => {
                const designDiv = document.createElement('div');
                designDiv.innerHTML = `<h3>${design.title}</h3><p>${design.description}</p>`;
                container.appendChild(designDiv);
            });
        }

        loadDesigns(aiDesigns, 'ai-designs-container');
        loadDesigns(techDesigns, 'tech-designs-container');

        // Form validation
        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;

            if (name && email && message) {
                alert('Thank you for your message!');
                document.getElementById('contact-form').reset();
            } else {
                alert('Please fill in all fields.');
            }
        });
    </script>
</body>
</html>

