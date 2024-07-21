<!DOCTYPE html>
<html>
<head>
    <link href="https://fonts.googleapis.com/css2?family=Space+Mono&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Space Mono', monospace;
            background-color: #f9f6ee;
            color: #3c3c3c;
        }
        #clock {
            text-align: center;
        }
        #time {
            font-size: 48px;
        }
        #date {
            font-size: 24px;
        }
    </style>
</head>
<body>
    <div id="clock">
        <h1 id="time"></h1>
        <p id="date"></p>
    </div>
    <script>
        function updateClock() {
            var now = new Date();
            var days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
            var dayOfWeek = days[now.getDay()];
            var month = now.getMonth() + 1;
            var day = now.getDate();
            var year = now.getFullYear();
            var hours = now.getHours();
            var minutes = now.getMinutes();
            var seconds = now.getSeconds();
            if (hours < 10) hours = '0' + hours;
            if (minutes < 10) minutes = '0' + minutes;
            if (seconds < 10) seconds = '0' + seconds;
            document.querySelector('#time').textContent = hours + ':' + minutes + ':' + seconds;
            document.querySelector('#date').textContent = dayOfWeek + ', ' + month + '/' + day + '/' + year;
        }
        setInterval(updateClock, 1000);
        updateClock();
    </script>
</body>
</html>
