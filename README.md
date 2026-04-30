<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>6th Grade English Exam - Unit 6</title>
    <style>
        body { font-family: Arial, sans-serif; line-height: 1.6; max-width: 800px; margin: 20px auto; padding: 20px; border: 1px solid #ccc; background-color: #f4f4f4; }
        .exam-container { background-color: #fff; padding: 30px; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        h1, h2 { text-align: center; color: #2c3e50; }
        .info-section { margin-bottom: 20px; padding: 15px; background: #eef2f3; border-radius: 5px; }
        .question { margin-bottom: 20px; padding: 15px; border-bottom: 1px solid #eee; }
        .reading-text { font-style: italic; background: #fffbe6; padding: 15px; border-left: 5px solid #f1c40f; margin-bottom: 15px; }
        .options { margin-top: 10px; }
        label { display: block; margin-bottom: 5px; cursor: pointer; }
        .submit-btn { display: block; width: 100%; padding: 15px; background: #27ae60; color: white; border: none; border-radius: 5px; font-size: 18px; cursor: pointer; }
        .submit-btn:hover { background: #219150; }
    </style>
</head>
<body>

<div class="exam-container">
    <h1>First English Exam</h1>
    <h2>Second Semester - 6th Grade</h2>

    <div class="info-section">
        <label for="studentName"><strong>Student Name:</strong></label>
        <input type="text" id="studentName" placeholder="Enter your full name" style="width: 100%; padding: 8px; margin-top: 5px;">
    </div>

    <form id="examForm">
        <!-- Q1: Reading -->
        <div class="question">
            <h3>Q1: Reading Comprehension (5 Marks)</h3>
            <div class="reading-text">
                It was the last day of their hiking holiday in the <strong>Dana Nature Reserve</strong>. Sami, his sister Eman and their dad were drinking cool water on top of a mountain. Eman wanted to hike down a narrow, rocky path. Her dad said, “Yes, but we must be careful! It’s very steep!”. Sami stay with Eman to keep her warm after her accident. Later, a rescue team took Eman back to the village.
            </div>
            <p>1. The family was in Wadi Mujib.</p>
            <div class="options">
                <label><input type="radio" name="q1_1" value="True"> True</label>
                <label><input type="radio" name="q1_1" value="False"> False</label>
                <label><input type="radio" name="q1_1" value="DS"> Doesn't Say</label>
            </div>
            <p>2. Eman wanted to take a narrow and steep path.</p>
            <div class="options">
                <label><input type="radio" name="q1_2" value="True"> True</label>
                <label><input type="radio" name="q1_2" value="False"> False</label>
            </div>
        </div>

        <!-- Q2: Vocabulary -->
        <div class="question">
            <h3>Q2: Vocabulary - Choose the correct word (5 Marks)</h3>
            <p>1. You should keep your bedroom __________.</p>
            <div class="options">
                <label><input type="radio" name="q2_1" value="tidy"> tidy</label>
                <label><input type="radio" name="q2_1" value="still"> still</label>
                <label><input type="radio" name="q2_1" value="fit"> fit</label>
            </div>
            <p>2. We didn't bring any __________, so we can't go rock climbing.</p>
            <div class="options">
                <label><input type="radio" name="q2_2" value="matches"> matches</label>
                <label><input type="radio" name="q2_2" value="rope"> rope</label>
                <label><input type="radio" name="q2_2" value="blanket"> blanket</label>
            </div>
        </div>

        <!-- Q3: Grammar -->
        <div class="question">
            <h3>Q3: Grammar - Indefinite Pronouns (5 Marks)</h3>
            <p>1. There's __________ in the shelter. They've gone hiking.</p>
            <div class="options">
                <label><input type="radio" name="q3_1" value="no one"> no one</label>
                <label><input type="radio" name="q3_1" value="anyone"> anyone</label>
                <label><input type="radio" name="q3_1" value="somewhere"> somewhere</label>
            </div>
            <p>2. Do you know __________ who has a tent?</p>
            <div class="options">
                <label><input type="radio" name="q3_2" value="anyone"> anyone</label>
                <label><input type="radio" name="q3_2" value="no one"> no one</label>
                <label><input type="radio" name="q3_2" value="nothing"> nothing</label>
            </div>
        </div>

        <!-- Q4: Equipment -->
        <div class="question">
            <h3>Q4: Matching Equipment (5 Marks)</h3>
            <p>1. It points north when you are lost.</p>
            <div class="options">
                <label><input type="radio" name="q4_1" value="Compass"> Compass</label>
                <label><input type="radio" name="q4_1" value="Penknife"> Penknife</label>
                <label><input type="radio" name="q4_1" value="Sleeping mat"> Sleeping mat</label>
            </div>
        </div>

        <button type="button" class="submit-btn" onclick="sendEmail()">Submit Answers via Email</button>
    </form>
</div>

<script>
    function sendEmail() {
        const name = document.getElementById('studentName').value;
        if (!name) {
            alert("Please enter your name first!");
            return;
        }

        let answers = "Student Name: " + name + "\n\nAnswers:\n";
        const formData = new FormData(document.getElementById('examForm'));
        
        for (let [key, value] of formData.entries()) {
            answers += key + ": " + value + "\n";
        }

        const subject = encodeURIComponent("English Exam Results - " + name);
        const body = encodeURIComponent(answers);
        
        // استبدل TEACHER@EMAIL.COM ببريدك الإلكتروني
        window.location.href = `mailto:TEACHER@EMAIL.COM?subject=${subject}&body=${body}`;
    }
</script>

</body>
</html>
