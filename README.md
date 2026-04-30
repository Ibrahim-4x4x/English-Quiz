# English-Quiz
Test
<T.Ibrahim>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Scouts Interactive Quiz</title>
    <style>
        :root {
            --primary-color: #1b5e20;
            --secondary-color: #4caf50;
            --bg-color: #f0f4f0;
            --text-color: #212121;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
        }
        .quiz-card {
            background: white;
            width: 100%;
            max-width: 800px;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        h1 {
            color: var(--primary-color);
            text-align: center;
            border-bottom: 3px solid var(--secondary-color);
            padding-bottom: 10px;
        }
        .question-box {
            margin-bottom: 30px;
            padding: 20px;
            border-left: 5px solid var(--secondary-color);
            background: #fafafa;
        }
        .question-text {
            font-weight: 600;
            font-size: 1.1rem;
            margin-bottom: 15px;
        }
        .option {
            display: block;
            margin: 10px 0;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
        }
        .option:hover {
            background-color: #e8f5e9;
        }
        input[type="radio"] {
            margin-right: 10px;
        }
        .submit-btn {
            display: block;
            width: 100%;
            padding: 15px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }
        .submit-btn:hover {
            background: var(--secondary-color);
        }
        #result-display {
            display: none;
            margin-top: 30px;
            padding: 20px;
            text-align: center;
            border-radius: 10px;
            font-size: 1.3rem;
        }
        .perfect { background: #c8e6c9; color: #2e7d32; }
        .good { background: #fff9c4; color: #f57f17; }
        .try-again { background: #ffcdd2; color: #c62828; }
    </style>
</head>
<body>

<div class="quiz-card">
    <h1>⚜️ Scouting Knowledge Quiz ⚜️</h1>
    <form id="scoutQuiz">
        <div id="questions-container"></div>
        <button type="button" class="submit-btn" onclick="checkQuiz()">Submit Answers</button>
    </form>
    <div id="result-display"></div>
</div>

<script>
const quizData = [
    { q: "In what year did the first Scout group for boys start in Jordan?", a: ["1954", "1907", "1960", "1945"], correct: 0 },
    { q: "Why do Scouts in Jordan clean parks and streets?", a: ["To get paid", "To help their community", "Because they are forced", "To win a race"], correct: 1 },
    { q: "Who was the founder of the global scouting movement?", a: ["Robert Baden-Powell", "King Abdullah I", "James West", "Ernest Thompson"], correct: 0 },
    { q: "What was the location of the 1907 scouting camp?", a: ["Amman", "Brownsea Island", "London", "Sydney"], correct: 1 },
    { q: "What activity do Australian scouts do to get a badge?", a: ["Cooking", "First-aid", "Singing", "Racing"], correct: 1 },
    { q: "How many bags of rubbish did the scouts pick up in the lesson?", a: ["Two", "Five", "Ten", "Twenty"], correct: 2 },
    { q: "Where do Scouts in England sleep according to the text?", a: ["In hotels", "In shelters", "In cars", "In schools"], correct: 1 },
    { q: "In what year did the Jordan Scout Association join the WOSM?", a: ["1954", "1960", "1970", "1980"], correct: 0 },
    { q: "What did scouts in Australia use to practice their emergency skills?", a: ["Sticks", "Bandages", "Phones", "Ropes"], correct: 1 },
    { q: "The organization started to include girls in which country's report?", a: ["Australia", "England", "Jordan", "USA"], correct: 2 },
    { q: "What do the Jordan Scouts teach young people about?", a: ["Gaming", "Community responsibilities", "Professional sports", "Shopping"], correct: 1 },
    { q: "What is a typical Scout uniform part?", a: ["Tie", "Neckerchief", "Swimming cap", "Mask"], correct: 1 },
    { q: "How did the scouts in England feel about sleeping in the forest?", a: ["They hated it", "It was fun", "They were scared", "It was boring"], correct: 1 },
    { q: "What was 'dirty' but the scouts 'cleaned it up'?", a: ["The street", "The park", "The school", "The beach"], correct: 1 },
    { q: "What did the scouts make that they described as 'great'?", a: ["A boat", "A campfire", "A house", "A map"], correct: 1 },
    { q: "What kind of activities does the Jordan Scout Association organize?", a: ["Indoor only", "Outdoor activities", "Online tests", "Math lessons"], correct: 1 },
    { q: "What is taught along with life skills and community responsibilities?", a: ["Music", "Responsibilities", "Dance", "Coding"], correct: 1 },
    { q: "Who can join the scouting activities according to the Jordan report?", a: ["Only adults", "Young people", "Only animals", "Only leaders"], correct: 1 },
    { q: "Where can you find answers about Robert Baden-Powell?", a: ["TV", "Internet", "Museum only", "Radio"], correct: 1 },
    { q: "Scouting teaches skills for which situation?", a: ["Emergencies", "Parties", "Sleeping", "Eating"], correct: 0 }
];

const container = document.getElementById('questions-container');
quizData.forEach((item, index) => {
    const div = document.createElement('div');
    div.className = 'question-box';
    div.innerHTML = `<div class="question-text">${index + 1}. ${item.q}</div>
        ${item.a.map((opt, i) => `
            <label class="option">
                <input type="radio" name="q${index}" value="${i}"> ${opt}
            </label>
        `).join('')}`;
    container.appendChild(div);
});

function checkQuiz() {
    let score = 0;
    quizData.forEach((item, index) => {
        const selected = document.querySelector(`input[name="q${index}"]:checked`);
        if (selected && parseInt(selected.value) === item.correct) score++;
    });

    const result = document.getElementById('result-display');
    result.style.display = 'block';
    result.innerHTML = `You scored ${score} out of 20!`;

    if (score === 20) {
        result.className = 'perfect';
        result.innerHTML += "<br>Master Scout! Perfect score! 🌟";
    } else if (score >= 12) {
        result.className = 'good';
        result.innerHTML += "<br>Great job! You know your scouts. 👍";
    } else {
        result.className = 'try-again';
        result.innerHTML += "<br>Keep reading the lesson and try again! 📚";
    }
    window.scrollTo({ top: 0, behavior: 'smooth' });
}
</script>
</body>
</html>
