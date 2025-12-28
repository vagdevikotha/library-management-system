# library-management-system
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Library Management System</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f6f9;
            text-align: center;
        }

        h1 {
            color: #2c3e50;
        }

        .container {
            margin: 20px;
        }

        input {
            padding: 10px;
            margin: 5px;
            width: 200px;
        }

        button {
            padding: 10px 15px;
            background-color: #3498db;
            border: none;
            color: white;
            cursor: pointer;
        }

        button:hover {
            background-color: #2980b9;
        }

        table {
            margin: auto;
            border-collapse: collapse;
            width: 60%;
        }

        th, td {
            border: 1px solid #ddd;
            padding: 10px;
        }

        th {
            background-color: #34495e;
            color: white;
        }

        .delete-btn {
            background-color: #e74c3c;
        }
    </style>
</head>
<body>

    <h1>📚 Library Management System</h1>

    <div class="container">
        <input type="text" id="bookName" placeholder="Book Name">
        <input type="text" id="authorName" placeholder="Author Name">
        <button onclick="addBook()">Add Book</button>
    </div>

    <table>
        <thead>
            <tr>
                <th>Book Name</th>
                <th>Author</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody id="bookList"></tbody>
    </table>

    <script>
        function addBook() {
            let bookName = document.getElementById("bookName").value;
            let authorName = document.getElementById("authorName").value;

            if (bookName === "" || authorName === "") {
                alert("Please fill all fields");
                return;
            }

            let table = document.getElementById("bookList");
            let row = table.insertRow();

            row.insertCell(0).innerHTML = bookName;
            row.insertCell(1).innerHTML = authorName;
            row.insertCell(2).innerHTML =
                '<button class="delete-btn" onclick="deleteBook(this)">Delete</button>';

            document.getElementById("bookName").value = "";
            document.getElementById("authorName").value = "";
        }

        function deleteBook(btn) {
            btn.parentElement.parentElement.remove();
        }
    </script>

</body>
</html>
