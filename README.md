<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Dynamic Webpage with DOM & jQuery Effects</title>

    <!-- jQuery CDN -->
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 40px;
        }

        #contentBox {
            width: 300px;
            margin: 20px auto;
            padding: 20px;
            background-color: lightblue;
            border-radius: 10px;
        }

        #animateBox {
            width: 100px;
            height: 100px;
            background-color: coral;
            margin: 20px auto;
            position: relative;
        }

        button {
            padding: 10px 15px;
            margin: 5px;
            cursor: pointer;
        }
    </style>
</head>

<body>

    <h1>Dynamic Webpage Demo</h1>

    <!-- Content Section -->
    <div id="contentBox">
        <p id="text">Click the button to change this content.</p>
    </div>

    <!-- Buttons -->
    <button onclick="changeContent()">Change Content (DOM)</button>
    <button id="hideBtn">Hide</button>
    <button id="showBtn">Show</button>
    <button id="toggleBtn">Toggle</button>
    <button id="animateBtn">Animate</button>

    <!-- Animated Box -->
    <div id="animateBox"></div>

    <script>
        // DOM Manipulation
        function changeContent() {
            document.getElementById("text").innerHTML =
                "🎉 The content has been updated dynamically using JavaScript DOM!";
        }

        // jQuery Effects
        $(document).ready(function () {

            // Hide
            $("#hideBtn").click(function () {
                $("#contentBox").hide(1000);
            });

            // Show
            $("#showBtn").click(function () {
                $("#contentBox").show(1000);
            });

            // Toggle
            $("#toggleBtn").click(function () {
                $("#contentBox").toggle(1000);
            });

            // Animate
            $("#animateBtn").click(function () {
                $("#animateBox").animate({
                    left: '200px',
                    height: '150px',
                    width: '150px',
                    opacity: '0.5'
                }, 1000).animate({
                    left: '0px',
                    height: '100px',
                    width: '100px',
                    opacity: '1'
                }, 1000);
            });

        });
    </script>

</body>
</html>
