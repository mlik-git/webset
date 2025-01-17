<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>form</title>
</head>

<body>
    <div class="box">
        <div class="click-warn">
            <p class="unselectable">
                <img src="click2.jpg" width="100px" title="小夏万岁">
            </p>
        </div>
        <div class="title">
            <p class="unselectable">Survey Form</p>
        </div>
        <div class="input-concent">
            <input type="text" placeholder="add content" class="click" id="inputBox"><!--
            --><button class="button">Add</button>
        </div>
        <div id="displayArea"></div>

    </div>
    <style>
        body {
            background: linear-gradient(to right,
                    rgb(62, 145, 212),
                    rgba(200, 70, 233, 0.541));
        }

        .click-warn {
            padding-top: 1px;
            margin-left: 10px;
            transition: transform 0.3s ease;
            border-color: #ccc;
            width: 40px;
            border-radius: 50px;
            background-size: cover;
        }

        .click-warn:active {
            transform: scale(0.85);
            
        }

        .box {
            width: 96%;
            height: 700px;
            background-color: #ffff;
            margin-top: 2%;
            box-sizing: border-box;
            margin-left: 2%;
            border-radius: 10px;
            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.55);

        }

        .unselectable {
            -webkit-user-select: none;
            /* Safari */
            -moz-user-select: none;
            /* Firefox */
            -ms-user-select: none;
            /* Internet Explorer/Edge */
            user-select: none;
            /* Non-prefixed version, currently supported by Chrome, Opera and Firefox */
            cursor: pointer;
            /* Change cursor to indicate clickability */
        }

        .title {
            text-align: center;
            padding-top: 20px;
            font-size: 35px;
            font-weight: 600;
            transition: transform 0.3s ease;
        }

        .title:active {
            transform: scale(0.95);
            color: #494545;
        }

        input {
            border-top-left-radius: 15px;
            border-bottom-left-radius: 15px;
            border: 1.5px solid rgb(221, 226, 230);
            width: 400px;
            height: 35px;
            outline: none;

        }

        .input-concent {
            padding-top: 30px;
            text-align: center;
        }

        button {
            width: 80px;
            height: 40px;
            border-top-right-radius: 15px;
            border-bottom-right-radius: 15px;
            background: linear-gradient(to right,
                    rgb(63, 191, 241),
                    rgba(250, 72, 226, 0.541));
            color: rgb(82, 88, 94);
            border: 1.5px solid rgb(221, 226, 230);

        }

        .button {
            transition: background-color 0.3s ease, transform 0.3s ease;
        }

        .button:active {
            transform: scale(0.9);
            background: linear-gradient(to right,
                    rgb(63, 220, 241),
                    rgba(250, 72, 131, 0.541));
        }

        .click {
            transition: transform 0.3s ease;
        }

        .click:active {
            transform: scale(0.98);
        }

        #displayArea {
            margin-top: 20px;
        }

        .displayItem {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 5px 0;
            padding-top: 5px;
            border: 1px solid #ccc;
            background-color: #ffff;
            color: rgb(82, 88, 94);
            transition: transform 0.3s ease;
        }

        .displayItem:active {
            transform: scale(0.98);
        }

        .deleteButton {
            cursor: pointer;
            color: red;
            text-align: right;

        }
    </style>
    <script>
        function submitText() {
            var inputText = document.getElementById('inputBox').value;

            if (inputText.trim() === '') {
                alert('请输入一些文本！');
                return;
            }

            var displayItem = document.createElement('div');
            displayItem.className = 'displayItem';

            var displayText = document.createElement('span');
            displayText.className = 'displayText';
            displayText.textContent = inputText;
            displayItem.appendChild(displayText);

            var deleteButton = document.createElement('button');
            deleteButton.className = 'deleteButton';
            deleteButton.textContent = '×'; // 这里可以用图标替换
            deleteButton.onclick = function () {
                displayItem.remove();
            };
            displayItem.appendChild(deleteButton);

            var displayArea = document.getElementById('displayArea');
            displayArea.appendChild(displayItem);

            document.getElementById('inputBox').value = '';
        }
    </script>
</body>

</html>
