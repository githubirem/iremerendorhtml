 <!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bil Ve Devam Et</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #fff;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #FFC0CB; /* Pembe */
            color: #fff;
            padding: 1em 0;
            text-align: center;
        }
        nav {
            background-color: #fff;
            border-bottom: 2px solid #FFC0CB; /* Pembe */
            padding: 1em 0;
            text-align: center;
        }
        nav a {
            color: #FFC0CB; /* Pembe */
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }
        .container {
            padding: 2em;
        }
        footer {
            background-color: #FFC0CB; /* Pembe */
            color: #fff;
            text-align: center;
            padding: 1em 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
        .game {
            background-color: #fff;
            border: 2px solid #FFC0CB; /* Pembe */
            border-radius: 5px;
            padding: 1em;
            margin: 2em 0;
        }
        .game h2 {
            color: #FFC0CB; /* Pembe */
        }
        .question {
            margin-bottom: 1em;
        }
        .options {
            list-style-type: none;
            padding: 0;
        }
        .options li {
            margin-bottom: 0.5em;
        }
        .options button {
            background-color: #FFC0CB; /* Pembe */
            color: #fff;
            border: none;
            padding: 10px;
            width: 100%;
            cursor: pointer;
            border-radius: 5px;
        }
        .options button:hover {
            background-color: #FF69B4; /* Daha koyu pembe */
        }
        #result {
            margin-top: 1em;
            font-weight: bold;
        }
    </style>
</head>
<body>

<header>
    <h1>Bil Ve Devam Et</h1>
</header>

<nav>
    <a href="#home">Ana Sayfa</a>
    <a href="#about">Hakkımda</a>
    <a href="#projects">Projelerim</a>
    <a href="#contact">İletişim</a>
</nav>

<div class="container" id="home">
    <section>
        <h2>Hoşgeldiniz!</h2>
        <p>Bu web sayfasında 25 soruluk bir oyun bulacaksınız. Bu sorular Irem ERENDOR  tarafindan hazirlanmistir Soruları cevaplayarak bilginizi test edin ve eğlenin!</p>
    </section>

    <section id="about">
        <h2>Hakkımda</h2>
        <p>Merhaba, ben Bil Ve Devam Et adlı oyunun yaratıcısı Irem ERENDOR . C++ kullanarak bu oyunu geliştirdim ve burada sizinle paylaşmaktan mutluluk duyuyorum.</p>
    </section>

    <section id="projects">
        <h2>Projelerim</h2>
        <div class="game">
            <h2>25 Soruluk Oyun</h2>
            <div id="game-container">
                <!-- Oyun burada yüklenecek -->
            </div>
            <div id="result"></div>
        </div>
    </section>

    <section id="contact">
        <h2>İletişim</h2>
        <p>Benimle iletişime geçmek için <a href="mailto:your-email@example.com">e-posta gönderin</a>.</p>
    </section>
</div>

<footer>
    <p>&copy; 2024 Bil Ve Devam Et. Tüm hakları saklıdır. GAME 310 final proje odevi icin olusturulmustur ticari bir amaci yoktur </p>
</footer>

<script>
    const questions = [
        {
            question: "What is the capital of France?",
            options: ["Paris", "London", "Berlin", "Madrid"],
            answer: 0
        },
        {
            question: "What is the speed of light in m/s?",
            options: ["299792458", "150000000", "300000000", "100000000"],
            answer: 0
        },
        {
            question: "What is 2 + 2?",
            options: ["3", "4", "5", "6"],
            answer: 1
        },
        {
            question: "What is the largest planet in our solar system?",
            options: ["Earth", "Mars", "Jupiter", "Saturn"],
            answer: 2
        },
        {
            question: "In which year did the Titanic sink?",
            options: ["1912", "1914", "1916", "1918"],
            answer: 0
        },
        {
            question: "Who wrote 'To Kill a Mockingbird'?",
            options: ["Harper Lee", "Mark Twain", "Ernest Hemingway", "F. Scott Fitzgerald"],
            answer: 0
        },
        {
            question: "What is the smallest prime number?",
            options: ["1", "2", "3", "5"],
            answer: 1
        },
        {
            question: "What is the chemical symbol for water?",
            options: ["HO", "H2O", "O2", "CO2"],
            answer: 1
        },
        {
            question: "What is the square root of 64?",
            options: ["6", "7", "8", "9"],
            answer: 2
        },
        {
            question: "Who painted the Mona Lisa?",
            options: ["Vincent van Gogh", "Pablo Picasso", "Leonardo da Vinci", "Claude Monet"],
            answer: 2
        },
        {
            question: "What is the fastest land animal?",
            options: ["Lion", "Tiger", "Cheetah", "Leopard"],
            answer: 2
        },
        {
            question: "What is the largest mammal?",
            options: ["Elephant", "Blue Whale", "Giraffe", "Orca"],
            answer: 1
        },
        {
            question: "What element does 'O' represent on the periodic table?",
            options: ["Osmium", "Oxygen", "Oganesson", "Oxonium"],
            answer: 1
        },
        {
            question: "Who discovered penicillin?",
            options: ["Marie Curie", "Alexander Fleming", "Isaac Newton", "Albert Einstein"],
            answer: 1
        },
        {
            question: "What is the capital of Japan?",
            options: ["Beijing", "Seoul", "Bangkok", "Tokyo"],
            answer: 3
        },
        {
            question: "How many continents are there?",
            options: ["5", "6", "7", "8"],
            answer: 2
        },
        {
            question: "What is the boiling point of water in Celsius?",
            options: ["90", "100", "110", "120"],
            answer: 1
        },
        {
            question: "Who wrote 'Romeo and Juliet'?",
            options: ["Charles Dickens", "William Shakespeare", "Jane Austen", "Mark Twain"],
            answer: 1
        },
        {
            question: "What is the hardest natural substance?",
            options: ["Gold", "Iron", "Diamond", "Silver"],
            answer: 2
        },
        {
            question: "What is the currency of the United Kingdom?",
            options: ["Euro", "Dollar", "Pound", "Franc"],
            answer: 2
        },
        {
            question: "Which planet is known as the Red Planet?",
            options: ["Earth", "Mars", "Jupiter", "Saturn"],
            answer: 1
        },
        {
            question: "Who was the first President of the United States?",
            options: ["Abraham Lincoln", "Thomas Jefferson", "John Adams", "George Washington"],
            answer: 3
        },
        {
            question: "What is the longest river in the world?",
            options: ["Amazon", "Nile", "Mississippi", "Yangtze"],
            answer: 1
        },
        {
            question: "In which year did World War II end?",
            options: ["1942", "1943", "1945", "1946"],
            answer: 2
        },
        {
            question: "What is the capital of Italy?",
            options: ["Venice", "Florence", "Milan", "Rome"],
            answer: 3
        }
    ];

    let currentQuestionIndex = 0;
    let score = 0;

    function loadQuestion() {
        if (currentQuestionIndex >= questions.length) {
            document.getElementById('result').innerText = `Oyun bitti! Skorunuz: ${score}/${questions.length}`;
            return;
        }

        const questionContainer = document.getElementById('game-container');
        questionContainer.innerHTML = '';

        const questionElement = document.createElement('div');
        questionElement.className = 'question';
        questionElement.innerText = questions[currentQuestionIndex].question;
        questionContainer.appendChild(questionElement);

        const optionsList = document.createElement('ul');
        optionsList.className = 'options';
        questions[currentQuestionIndex].options.forEach((option, index) => {
            const optionItem = document.createElement('li');
            const optionButton = document.createElement('button');
            optionButton.innerText = option;
            optionButton.onclick = () => checkAnswer(index);
            optionItem.appendChild(optionButton);
            optionsList.appendChild(optionItem);
        });
        questionContainer.appendChild(optionsList);
    }

    function checkAnswer(selectedIndex) {
        if (selectedIndex === questions[currentQuestionIndex].answer) {
            score++;
        }
        currentQuestionIndex++;
        loadQuestion();
    }

    loadQuestion();
</script>

</body>
</html>
