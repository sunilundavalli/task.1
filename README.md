<!DOCTYPE html>
<html>
<head>
  <title>To-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    
    .container {
      max-width: 400px;
      margin: 20px auto;
    }
    
    .title {
      text-align: center;
      font-size: 24px;
      margin-bottom: 20px;
    }
    
    .todo-input {
      display: flex;
      margin-bottom: 10px;
    }
    
    .todo-input input[type="text"] {
      flex-grow: 1;
      padding: 10px;
      font-size: 16px;
    }
    
    .todo-input button {
      padding: 10px;
      background-color: #4caf50;
      color: #fff;
      border: none;
      font-size: 16px;
    }
    
    .todo-list {
      list-style-type: none;
      padding: 0;
    }
    
    .todo-list li {
      display: flex;
      align-items: center;
      margin-bottom: 10px;
    }
    
    .todo-list li .todo-item {
      flex-grow: 1;
      padding: 10px;
      font-size: 16px;
    }
    
    .todo-list li button {
      padding: 5px;
      background-color: #f44336;
      color: #fff;
      border: none;
      font-size: 14px;
      cursor: pointer;
    }
  </style>
  <script>
    function addTodo() {
      var input = document.getElementById("todoInput");
      var todoList = document.getElementById("todoList");
      
      var todoItem = input.value;
      if (todoItem.trim() !== "") {
        var li = document.createElement("li");
        li.innerHTML = '<span class="todo-item">' + todoItem + '</span><button onclick="removeTodo()">Remove</button>';
        todoList.appendChild(li);
        input.value = "";
      }
    }
    
    function removeTodo() {
      var todoItem = event.target.parentNode;
      var todoList = document.getElementById("todoList");
      todoList.removeChild(todoItem);
    }
  </script>
</head>
<body>
  <div class="container">
    <h1 class="title">To-Do List</h1>
    <div class="todo-input">
      <input type="text" id="todoInput" placeholder="Enter a task">
      <button onclick="addTodo()">Add</button>
    </div>
    <ul id="todoList" class="todo-list"></ul>
  </div>
</body>
</html>
