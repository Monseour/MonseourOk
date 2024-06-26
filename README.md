<!DOCTYPE html>
<html>
<head>
    <title>My Computer Shop System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .container {
            width: 50%;
            margin: auto;
            overflow: hidden;
        }
        header {
            background: #50b3a2;
            color: #fff;
            padding-top: 30px;
            min-height: 70px;
            border-bottom: #e8491d 3px solid;
        }
        header a {
            color: #fff;
            text-decoration: none;
            text-transform: uppercase;
            font-size: 16px;
        }
        header ul {
            padding: 0;
            list-style: none;
        }
        header li {
            display: inline;
            padding: 0 20px 0 20px;
        }
        .main {
            padding: 15px;
            background: #fff;
            margin-top: 20px;
        }
        .main h2 {
            color: #333;
        }
        .form-group {
            margin-bottom: 15px;
        }
        .form-group label {
            display: block;
            margin-bottom: 5px;
        }
        .form-group select, .form-group input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .btn {
            display: inline-block;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            text-align: center;
            text-decoration: none;
            outline: none;
            color: #fff;
            background-color: #50b3a2;
            border: none;
            border-radius: 5px;
            box-shadow: 0 9px #999;
        }
        .btn:hover {background-color: #3e8e7e}
        .btn:active {
            background-color: #3e8e7e;
            box-shadow: 0 5px #666;
            transform: translateY(4px);
        }
        #computerSelection, #timeSelection, #summary {
            display: none;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>Welcome to My Computer Shop</h1>
        </div>
    </header>

    <div class="container main">
        <div id="proceedSection">
            <h2>Do you want to proceed? (Y/N)</h2>
            <div class="form-group">
                <label for="proceed">Please select:</label>
                <select id="proceed">
                    <option value="Y">Yes</option>
                    <option value="N">No</option>
                </select>
            </div>
            <button class="btn" onclick="checkProceed()">Submit</button>
        </div>

        <div id="computerSelection">
            <h2>Select a Vacant Computer</h2>
            <div class="form-group">
                <label for="computer">List of vacant computers:</label>
                <select id="computer">
                    <option value="1">Computer 1</option>
                    <option value="2">Computer 2</option>
                    <option value="3">Computer 3</option>
                    <option value="4">Computer 4</option>
                    <option value="5">Computer 5</option>
                </select>
            </div>
            <button class="btn" onclick="showTimeSelection()">Next</button>
        </div>

        <div id="timeSelection">
            <h2>Select Time and Price</h2>
            <div class="form-group">
                <label for="time">List of hours and its price:</label>
                <select id="time">
                    <option value="15">1 hour - 15 pesos</option>
                    <option value="25">2 hours - 25 pesos</option>
                    <option value="40">3 hours - 40 pesos</option>
                    <option value="55">4 hours - 55 pesos</option>
                    <option value="65">5 hours - 65 pesos</option>
                </select>
            </div>
            <button class="btn" onclick="showSummary()">Proceed</button>
        </div>

        <div id="summary" style="margin-top: 20px;">
            <h2>Summary of Payment</h2>
            <p id="summaryText"></p>
        </div>
    </div>

    <script>
        function checkProceed() {
            const proceed = document.getElementById('proceed').value;
            if (proceed === 'Y') {
                document.getElementById('proceedSection').style.display = 'none';
                document.getElementById('computerSelection').style.display = 'block';
            } else {
                alert('Thank you! Come again.');
            }
        }

        function showTimeSelection() {
            document.getElementById('computerSelection').style.display = 'none';
            document.getElementById('timeSelection').style.display = 'block';
        }

        function showSummary() {
            const computer = document.getElementById('computer').value;
            const timeSelect = document.getElementById('time');
            const time = timeSelect.options[timeSelect.selectedIndex].text;
            const price = timeSelect.value;

            document.getElementById('summaryText').innerText = `You chose computer ${computer}. The cost for ${time} is ${price} pesos. 
			Please wait for your ticket and go to the counter to pay.
			Thank you!`;
            document.getElementById('summary').style.display = 'block';
        }
    </script>
</body>
</html>
s
