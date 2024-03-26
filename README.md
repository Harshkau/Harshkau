- 👋 Hi, I’m<b> Harsh kaushik</b>
- <br>
- 🌱<strong> currently I’m  learning:</strong> java script 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>

      body {
    font-family: Arial, sans-serif;
    background: rgb(44, 179, 233);
    
}

.container {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
}

input[type="text"] {
    width: 70%;
    padding: 8px;
    margin-bottom: 10px;
}

button {
    padding: 8px 16px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    padding: 8px 0;
    border-bottom: 1px solid #ddd;
}

li:last-child {
    border-bottom: none;
}

    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Add new task">
        <button onclick="addTask()">Add Task</button>
        <ul id="taskList"></ul>
    </div>

    <script>
      function addTask() {
    var taskInput = document.getElementById('taskInput');
    var taskList = document.getElementById('taskList');

    if (taskInput.value === '') {
        document.write("Please enter a task!");
        return;
    }

    var li = document.createElement('li');
    li.textContent = taskInput.value;
    taskList.appendChild(li);

    taskInput.value = '';

    // Add event listener to mark task as completed
    li.addEventListener('click', function() {
        li.classList.toggle('completed');
    });

    // Add delete button to each task
    var deleteButton = document.createElement('button');
    deleteButton.textContent = 'Delete';
    deleteButton.className = 'delete';
    li.appendChild(deleteButton);

    // Add event listener to delete task
    deleteButton.addEventListener('click', function() { li.remove(); });
}

    </script>
</body>
</html>
