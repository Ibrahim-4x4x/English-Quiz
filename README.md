<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>6th Grade English Exam - Semester 2</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f0f2f5; color: #333; line-height: 1.6; padding: 20px; }
        .exam-paper { max-width: 850px; margin: auto; background: white; padding: 40px; border-radius: 10px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); border-top: 10px solid #2980b9; }
        .header { text-align: center; border-bottom: 2px solid #eee; margin-bottom: 30px; padding-bottom: 20px; }
        .student-info { background: #f9f9f9; padding: 20px; border-radius: 5px; margin-bottom: 30px; border: 1px solid #ddd; }
        .question-box { margin-bottom: 30px; padding: 20px; border: 1px solid #eee; border-radius: 8px; transition: 0.3s; }
        .question-box:hover { border-color: #3498db; }
        .question-title { font-weight: bold; color: #2c3e50; font-size: 1.1em; margin-bottom: 15px; display: block; }
        .reading-text { background: #fffbe6; padding: 20px; border-left: 5px solid #f1c40f; font-style: italic; margin-bottom: 20px; line-height: 1.8; }
        .options { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 10px; }
        label { background: #fff; border: 1px solid #ddd; padding: 10px; border-radius: 5px; cursor: pointer; display: flex; align-items: center; }
        label:hover { background: #e8f4fd; }
        input[type="radio"] { margin-right: 10px; }
        .submit-section { text-align: center; margin-top: 50px; }
        .btn-send { background: #27ae60; color: white; border: none; padding: 15px 40px; font-size: 1.2em; border-radius: 30px; cursor: pointer; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .btn-send:hover { background: #219150; transform: translateY(-2px); }
    </style>
</head>
<body>

<div class="exam-paper">
    <div class="header">
        <h1>First English Exam - Second Semester</h1>
        <p>Grade 6 | Unit 6: Adventures</p>
    </div>

    <div class="student-info">
        <label for="studentName" style="background:transparent; border:none; font-weight:bold;">Student Full Name:</label>
        <input type="text" id="studentName" placeholder="Type your name here..." style="width: 100%; padding: 12px; border: 1px solid #ccc; border-radius: 4px; font-size: 16px;">
    </div>

    <form id="examForm">
        <!-- Q1: Reading Comprehension -->
        <div class="question-box">
            <span class="question-title">Q1: Read the text and choose the correct answer (T, F, or DS). (5 Marks)</span>
            <div class="reading-text">
                It was the last day of their hiking holiday in the <strong>Dana Nature Reserve</strong>. Sami, his sister Eman and their dad were drinking cool water on top of a mountain. Eman wanted to hike down a narrow, rocky path. Her dad said, “Yes, but we must be careful! It’s very steep!”. While they were walking, they found Eman on the ground. She’d had an accident! Sami said, “Keep still! You mustn’t move. I learned <strong>first aid</strong> at school”. Dad ran for help while Sami stayed with Eman.
            </div>
            
            <p>1. The family was enjoying the views in Wadi Mujib.</p>
            <div class="options">
                <label><input type="radio" name="q1_1" value="True"> True</label>
                <label><input type="radio" name="q1_1" value="False"> False</label>
                <label><input type="radio" name="q1_1" value="DS"> Doesn't Say</label>
            </div>

            <p style="margin-top:20px;">2. Sami knew first aid because he studied it at school.</p>
            <div class="options">
                <label><input type="radio" name="q1_2" value="True"> True</label>
                <label><input type="radio" name="q1_2" value="False"> False</label>
                <label><input type="radio" name="q1_2" value="DS"> Doesn't Say</label>
            </div>
        </div>

        <!-- Q2: Vocabulary -->
        <div class="question-box">
            <span class="question-title">Q2: Choose the correct word to complete the sentence. (5 Marks)</span>
            
            <p>1. Don’t be messy! You should keep your bedroom __________.</p>
            <div class="options">
                <label><input type="radio" name="q2_1" value="tidy"> tidy</label>
                <label><input type="radio" name="q2_1" value="still"> still</label>
                <label><input type="radio" name="q2_1" value="fit"> fit</label>
            </div>

            <p style="margin-top:20px;">2. We didn’t bring any __________, so we can’t go rock climbing.</p>
            <div class="options">
                <label><input type="radio" name="q2_2" value="rope"> rope</label>
                <label><input type="radio" name="q2_2" value="matches"> matches</label>
                <label><input type="radio" name="q2_2" value="plaster"> plaster</label>
            </div>
        </div>

        <!-- Q3: Grammar -->
        <div class="question-box">
            <span class="question-title">Q3: Grammar - Choose the correct indefinite pronoun or modal. (5 Marks)</span>
            
            <p>1. There’s __________ in the shelter. They’ve all gone hiking today.</p>
            <div class="options">
                <label><input type="radio" name="q3_1" value="no one"> no one</label>
                <label><input type="radio" name="q3_1" value="anyone"> anyone</label>
                <label><input type="radio" name="q3_1" value="someone"> someone</label>
            </div>

            <p style="margin-top:20px;">2. You __________ move! You have hurt your leg.</p>
            <div class="options">
                <label><input type="radio" name="q3_2" value="mustn't"> mustn't</label>
                <label><input type="radio" name="q3_2" value="should"> should</label>
                <label><input type="radio" name="q3_2" value="need to"> need to</label>
            </div>
        </div>

        <!-- Q4: Equipment -->
        <div class="question-box">
            <span class="question-title">Q4: Equipment Identification - Choose the correct item. (5 Marks)</span>
            
            <p>1. You use this when you’re lost. It points north.</p>
            <div class="options">
                <label><input type="radio" name="q4_1" value="Compass"> Compass</label>
                <label><input type="radio" name="q4_1" value="Penknife"> Penknife</label>
                <label><input type="radio" name="q4_1" value="Blanket"> Blanket</label>
            </div>

            <p style="margin-top:20px;">2. You can cook on this. You don’t need a fire.</p>
            <div class="options">
                <label><input type="radio" name="q4_2" value="Camping stove"> Camping stove</label>
                <label><input type="radio" name="q4_2" value="Sleeping mat"> Sleeping mat</label>
                <label><input type="radio" name="q4_2" value="Rucksack"> Rucksack</label>
            </div>
        </div>

        <div class="submit-section">
            <button type="button" class="btn-send" onclick="sendToTeacher()">Submit via Email</button>
        </div>
    </form>
</div>

<script>
    function sendToTeacher() {
        const name = document.getElementById('studentName').value;
        if (!name) {
            alert("Please enter your name first!");
            return;
        }

        const teacherEmail = "TEACHER@EMAIL.COM"; // ضع إيميل المعلم هنا
        let body = "Student Name: " + name + "\n\n--- Exam Answers ---\n";
        
        const form = document.getElementById('examForm');
        const formData = new FormData(form);
        
        for (let [key, value] of formData.entries()) {
            body += key.toUpperCase() + ": " + value + "\n";
        }

        const subject = encodeURIComponent("English Exam Result: " + name);
        const mailtoLink = `mailto:${teacherEmail}?subject=${subject}&body=${encodeURIComponent(body)}`;
        
        window.location.href = mailtoLink;
    }
</script>

</body>
</html>
