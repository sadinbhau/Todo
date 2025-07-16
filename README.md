<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>ToDo App</title>
  <style>
    body { font-family: Arial; padding: 20px; }
    input, button { padding: 10px; margin: 5px; }
    li { list-style: none; margin: 10px 0; }
  </style>
</head>
<body>
  <h1>📝 My ToDo List</h1>
  <input id="taskInput" type="text" placeholder="Enter task..." />
  <button onclick="addTask()">Add</button>
  <ul id="taskList"></ul>

  <script>
    function addTask() {
      const input = document.getElementById('taskInput');
      const task = input.value.trim();
      if (task === '') return;

      const li = document.createElement('li');
      li.innerHTML = `
        ${task}
        <button onclick="this.parentElement.remove()">❌</button>
      `;
      document.getElementById('taskList').appendChild(li);
      input.value = '';
    }
  </script>
</body>
</html>
