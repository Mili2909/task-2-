<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A simple input form with validation and a dynamic to-do list.">
    <meta name="keywords" content="input form, validation, to-do list, HTML, CSS, JavaScript">
    <meta name="author" content="MILI">
  <title>INPUT FORM</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f7fa;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .form-container {
      background: #fff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      width: 350px;
    }

    .form-container h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    }

    .form-group {
      margin-bottom: 15px;
    }

    .form-group label {
      display: block;
      margin-bottom: 6px;
      font-weight: bold;
    }

    .form-group input[type="text"],
    .form-group input[type="email"] {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 14px;
    }

    .form-group input[type="submit"] {
      width: 100%;
      padding: 12px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .form-group input[type="submit"]:hover {
      background-color: #45a049;
    }
     nav {
      background-color: #333;
      color: gray;
      padding: 15px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }

    nav .logo {
      font-size: 1.4rem;
      font-weight: bold;
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 20px;
      padding: 0;
      margin: 0;
    }

    nav ul li {
      cursor: pointer;
    }

    nav ul li:hover {
      text-decoration: underline;
    }
    
    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      padding: 20px;
    }

    .box {
      background-color:grey;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
      text-align: center;
    }

    .box h3 {
      margin-top: 0;
    }

    @media (max-width: 900px) {
      .container {
        grid-template-columns  : repeat(2, 1fr);
      }
    }

    @media (max-width: 600px) {
      nav {
        flex-direction: column;
        align-items: flex-start;
      }

      nav ul {
        flex-direction: column;
        gap: 10px;
        margin-top: 10px;
      }

      .container {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

  <!-- Flexbox Navigation -->
  <nav>
    <div class="logo">MyWebsite</div>
    <ul>
        <br>
      <li>Home</li>
      <li>About</li>
      <li>Services</li>
      <li>Contact</li>
    </ul>
  </nav>
  <br>

  <!-- CSS Grid Content Area -->
  <div class="container">
    <div class="box">
      <h3>Box 1</h3>
      <p>class 1</p>
    </div>
    <div class="box">
      <h3>Box 2</h3>
      <p>class 2</p>
    </div>
    <div class="box">
      <h3>Box 3</h3>
      <p>class 3</p>
    </div>
    <div class="box">
      <h3>Box 4</h3>
      <p>class 4</p>
    </div>
    <div class="box">
      <h3>Box 5</h3>
      <p>class 5</p>
    </div>
    <div class="box">
      <h3>Box 6</h3>
      <p>class 6</p>
    </div>
  </div>
  </style>
</head>
<br>
<body>

  <div class="form-container">
    <h2>Contact Form</h2>
    <form action="#" method="POST">
      <div class="form-group">
        <label for="name">Full Name</label>
        <input type="text" id="name" name="fullname" placeholder="Enter your name" required>
      </div>

      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" name="email" placeholder="Enter your email" required>
      </div>

      <div class="form-group">
        <input type="submit" value="Submit">
      </div>
    </form>
  </div>
  <!-- form validation  -->
 <script>
    document.getElementById('contactForm').addEventListener('submit', function(e) {
      e.preventDefault(); 

      document.getElementById('nameError').textContent = '';
      document.getElementById('emailError').textContent = '';

      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();

      let isValid = true;

      if (name === '') {
        document.getElementById('nameError').textContent = 'Full Name is required.';
        isValid = false;
      }

      const emailPattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
      if (email === '') {
        document.getElementById('emailError').textContent = 'Email is required.';
        isValid = false;
      } else if (!emailPattern.test(email)) {
        document.getElementById('emailError').textContent = 'Enter a valid email address.';
        isValid = false;
      }


      if (isValid) {
        alert('Form submitted successfully!');
        document.getElementById('contactForm').reset(); 
      }
    });
  </script>
  <!-- dynamic to do list  -->
   <br>
   <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 40px;
    }

    .todo-container {
      background: #fff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      width: 100%;
      max-width: 400px;
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    }

    .input-group {
      display: flex;
      gap: 10px;
    }

    input[type="text"] {
      flex: 1;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }

    button {
      padding: 10px 14px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }

    button:hover {
      background-color: #45a049;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }

    li {
      padding: 10px;
      background: #eee;
      border-radius: 6px;
      margin-bottom: 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .delete-btn {
      background: crimson;
      color: white;
      border: none;
      padding: 5px 10px;
      border-radius: 6px;
      cursor: pointer;
    }

    .delete-btn:hover {
      background: darkred;
    }
  </style>
</head>
<body>

  <div class="todo-container">
    <h2>To-Do List</h2>
    <div class="input-group">
      <input type="text" id="taskInput" placeholder="Enter a new task">
      <button onclick="addTask()">Add</button>
    </div>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const taskText = input.value.trim();

      if (taskText === "") {
        alert("Task cannot be empty!");
        return;
      }

      const li = document.createElement("li");
      li.textContent = taskText;

      const deleteBtn = document.createElement("button");
      deleteBtn.textContent = "Delete";
      deleteBtn.className = "delete-btn";
      deleteBtn.onclick = () => li.remove();

      li.appendChild(deleteBtn);
      document.getElementById("taskList").appendChild(li);

      input.value = ""; 
    }
  </script>
</body>
</html>
