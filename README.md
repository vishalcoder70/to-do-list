# to-do-list
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My To-Do List App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #667eea, #764ba2);
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .container {
      background: rgba(0, 0, 0, 0.4);
      padding: 20px;
      border-radius: 12px;
      width: 360px;
      box-shadow: 0 6px 18px rgba(0,0,0,0.35);
    }
    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #ffd369;
    }
    .input-box {
      display: flex;
      margin-bottom: 15px;
    }
    input {
      flex: 1;
      padding: 12px;
      border: none;
      border-radius: 6px 0 0 6px;
      outline: none;
      font-size: 14px;
    }
    button {
      padding: 12px 18px;
      border: none;
      background: #ff6b6b;
      color: white;
      border-radius: 0 6px 6px 0;
      cursor: pointer;
      font-weight: bold;
      transition: 0.3s;
    }
    button:hover {
      background: #ff4757;
    }
    ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }
    li {
      background: rgba(255,255,255,0.15);
      margin-bottom: 10px;
      padding: 10px;
      border-radius: 6px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      transition: 0.3s;
    }
    li.completed {
      text-decoration: line-through;
      opacity: 0.6;
    }
    .delete-btn {
      background: transparent;
      color: #ff6b6b;
      border: none;
      cursor: pointer;
      font-size: 16px;
    }
    .delete-btn:hover {
      color: #ff4040;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>🌟 My To-Do List 🌟</h2>
    <div class="input-box">
      <input type="text" id="taskInput" placeholder="Add a new task...">
      <button onclick="addTask()">Add</button>
    </div>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      let input = document.getElementById("taskInput");
      let taskText = input.value.trim();
      if (taskText === "") return;

      let li = document.createElement("li");
      li.innerHTML = `
        <span onclick="this.parentElement.classList.toggle('completed')">${taskText}</span>
        <button class="delete-btn" onclick="this.parentElement.remove()">✖</button>
      `;
      document.getElementById("taskList").appendChild(li);
      input.value = "";
    }
  </script>
</body>
</html>
