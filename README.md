# greenie-project
web design
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Management Dashboard</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        .dashboard {
            max-width: 800px;
            margin: 20px auto;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        .tabs {
            display: flex;
            border-bottom: 1px solid #ccc;
        }

        .tab {
            flex: 1;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            background-color: #eee;
            border-right: 1px solid #ccc;
        }

        .tab:last-child {
            border-right: none;
        }

        .content {
            padding: 20px;
        }

        /* Style for the User Details Table */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }

        th {
            background-color: #f2f2f2;
        }

        /* Style for the Account Creation Form */
        form {
            max-width: 400px;
            margin: 20px auto;
        }

        label {
            display: block;
            margin-bottom: 8px;
        }

        input {
            width: 100%;
            padding: 8px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        button {
            background-color: #4caf50;
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <div class="tabs">
            <div class="tab" onclick="showTab('userDetails')">User Details</div>
            <div class="tab" onclick="showTab('accountCreation')">AccountCreation</div>
        </div>

        <div class="content" id="userDetails"{ display: tab === 'userdetails' ? 'block' : 'none' }}>>
            <h2>User Details</h2>
            <table>
                <thead>
                    <tr>
                        <th>Username</th>
                        <th>Email</th>
                        <th>Phone</th>
                        <th>ID</th>
                        <th>Creation Date</th>
                    </tr>
                </thead>
                <tbody>
                    
                    <tr>
                        <td>sekhar ch</td>
                        <td>chemalapallisekhar02101999@gmail.com</td>
                        <td>9502039517</td>
                        <td>112233</td>
                        <td>15-11-2023</td>
                    </tr>
                    
                </tbody>
            </table>
        </div>
  <div className="content" id="accountCreation" style={{ display: tab === 'accountCreation' ? 'block' : 'none' }}>
        <h2>Account Creation</h2>
        <form onSubmit={handleFormSubmit}>
          <label htmlFor="username">Username:</label>
          <input type="text" id="username" name="username" required />

          <label htmlFor="password">Password:</label>
          <input type="password" id="password" name="password" required />

          <button type="submit">Create Account</button>
        </form>
      </div>
    </div>

    <script>
        function showTab(tabName) {
            const tabs = document.querySelectorAll('.tab');
            const contents = document.querySelectorAll('.content');

            tabs.forEach(tab => tab.classList.remove('active'));
            contents.forEach(content => content.style.display = 'none');

            const selectedTab = document.querySelector(`.tab:contains('${tabName}')`);
            const selectedContent = document.getElementById(`${tabName}Content`);

            selectedTab.classList.add('active');
            selectedContent.style.display = 'block';
        }

        
        jQuery.expr[':'].contains = function (a, i, m) {
            return jQuery(a).text().toUpperCase()
                .indexOf(m[3].toUpperCase()) >= 0;
        };

        
        showTab('userDetails');
    </script>
</body>
</html>
