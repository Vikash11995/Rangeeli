## code of the Website


```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            display: flex;
            justify-content: center; /* Centering content horizontally */
            align-items: center; /* Centering content vertically */
            height: 100vh; /* Full viewport height */
        }
        .container {
            height: 30vh;
            width: 60vw;
            text-align: center;
            background-color: transparent;
            padding: 20px;
            border-radius: 10px;
            box-shadow:  8px -4px 8px rgba(0, 0, 0, 0.2);
            gap: 20px;
            display: flex;
            grid-template-rows: repeat(2, 1fr); /* Added to enable grid layout */
            align-items: center;
            justify-content: center; /* Centering content horizontally */
            flex-direction: column; /* Added to stack items vertically */
            border: 1px solid #333; /* Added border */
        }
        .actionBtn {
            
            font-family: Arial, sans-serif;
            margin-top: 20px;
            gap: 40px;
            display: grid; /* Added to enable grid layout */
            grid-template-columns: repeat(2, 1fr); /* Added to create two equal columns */
            margin-left: calc(100% -40vw); /* Centering the buttons horizontally */
            
        }
        .actionBtn button {
            padding: 10px 20px;
            width: 100%;
            font-size: 16px;
            border: none;

            border-radius: 10px;
            background-color: #007BFF;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
      #stop:hover{
background-color: red;
      }
        #start:hover {
            background-color: green;
        }
        #heading {
            font-family: Arial, sans-serif;
            font-size: 24px;
            color: #333;
            margin-bottom: 20px;
        }
        @media (max-width: 600px) {
            .container {
                width: 90vw; /* Adjust width for smaller screens */
                height: 40vh; /* Adjust height for smaller screens */
            }
            .actionBtn {
                grid-template-columns: 1fr; /* Stack buttons vertically on small screens */
                gap: 10px; /* Reduce gap between buttons */
            }
      }
    </style>
</head>

<body>
    <div class="container">
        <h1 id="heading">The color changing Website</h1>
        <div class="actionBtn">
            <button type="button" id="start">Start</button>
            <button type="button" id="stop">Stop</button></div>
    </div>
    
</body>
<script>
    const randomColour = function () {
        const hex = '0123456789ABCDEF';
        let color = '#';
        for (let i = 0; i <= 5; i++) {
            color += hex[Math.floor(Math.random() * 16)]
        }
        return color;
    }
    let text = randomColour();
    console.log(text)
let intervalId; 
let startChangingColor = function (){
intervalId = setInterval(changeBg,1000);
    function changeBg(){
           document.body.style.backgroundColor = randomColour()
              document.getElementById('heading').innerText = "Color-Code is " + randomColour();
    }
}
const stopChangingColor = function (){
    clearInterval(intervalId);
}
document.getElementById('start').addEventListener('click',
    startChangingColor);
document.getElementById('stop').addEventListener('click',
    stopChangingColor);
</script>

</html>

```
