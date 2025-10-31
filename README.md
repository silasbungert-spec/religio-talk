<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KinderReligionForum</title>
<style>
    body {
        font-family: 'Comic Sans MS', sans-serif;
        margin: 0;
        background: linear-gradient(to right, #fdfbfb, #ebedee);
        color: #333;
    }
    header {
        background-color: #ff6f61;
        color: white;
        text-align: center;
        padding: 20px;
        font-size: 2em;
        box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }
    main {
        max-width: 800px;
        margin: 20px auto;
        padding: 0 20px;
    }
    .post-form {
        background-color: #fff3b0;
        padding: 15px;
        border-radius: 12px;
        margin-bottom: 20px;
        box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }
    .post-form input, .post-form textarea, .post-form select {
        width: 100%;
        padding: 10px;
        margin: 8px 0;
        border-radius: 6px;
        border: 1px solid #ccc;
        font-size: 1em;
    }
    .post-form button {
        background-color: #6ec1e4;
        border: none;
        padding: 10px 20px;
        color: white;
        font-weight: bold;
        border-radius: 6px;
        cursor: pointer;
    }
    .post {
        background-color: #d0f0c0;
        padding: 15px;
        border-radius: 12px;
        margin-bottom: 15px;
        box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }
    .post h3 {
        margin: 0 0 10px 0;
    }
    .comments {
        margin-top: 10px;
        padding-left: 20px;
    }
    .comment {
        background-color: #ffe0e0;
        padding: 8px;
        border-radius: 8px;
        margin-bottom: 5px;
        font-size: 0.95em;
    }
    .comment input {
        width: 100%;
        padding: 8px;
        margin-top: 5px;
        border-radius: 6px;
        border: 1px solid #ccc;
    }
</style>
</head>
<body>

<header>KinderReligionForum 🌈</header>

<main>
    <div class="post-form">
        <h2>Stelle eine Frage</h2>
        <input type="text" id="username" placeholder="Dein Name">
        <select id="religion">
            <option value="">Religion auswählen</option>
            <option>Christentum</option>
            <option>Islam</option>
            <option>Judentum</option>
            <option>Buddhismus</option>
            <option>Hinduismus</option>
            <option>Andere</option>
        </select>
        <textarea id="question" rows="4" placeholder="Deine Frage hier eingeben"></textarea>
        <button onclick="postQuestion()">Frage posten</button>
    </div>

    <div id="posts">
        <!-- Fragen erscheinen hier -->
    </div>
</main>

<script>
    function postQuestion() {
        const username = document.getElementById('username').value || "Anonym";
        const religion = document.getElementById('religion').value || "Allgemein";
        const question = document.getElementById('question').value;
        if (!question) return alert("Bitte schreibe eine Frage!");

        const postDiv = document.createElement('div');
        postDiv.className = 'post';
        postDiv.innerHTML = `
            <h3>${username} fragt über ${religion}:</h3>
            <p>${question}</p>
            <div class="comments">
                <input type="text" placeholder="Kommentar schreiben..." onkeypress="if(event.key==='Enter'){addComment(this)}">
            </div>
        `;

        document.getElementById('posts').prepend(postDiv);

        // Felder leeren
        document.getElementById('username').value = '';
        document.getElementById('religion').value = '';
        document.getElementById('question').value = '';
    }

    function addComment(input) {
        const commentText = input.value;
        if (!commentText) return;
        const commentDiv = document.createElement('div');
        commentDiv.className = 'comment';
        commentDiv.textContent = commentText;

        input.parentElement.appendChild(commen-tDiv);
        input.value = '';
    }
</script>

</body>
</html>
