<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            padding: 0;
            margin: 0;
            box-sizing: border-box;
        }
        body{
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(to top,rgb(0,0,0,0.9)50%,rgb(0,0,0,0.9)50%);
            min-height: 100vh;
            background: radial-gradient(#555,#111);
        }
        .bulb{
            display: flex;
            height:80px ;
            width: 80px;
            background: #444;
            border-radius: 50%;
            position: relative;
            z-index: 2;
        }
        .bulb::before{
            content: " ";
            position: absolute;
            width: 35px;
            left: 22.5px;
            top: -50px;
            height: 80px;
            background:var(--beforeback,#444);
            border-top: 30px solid#000;
            border-radius: 10px;
            transition: 0.6s ease;
        }
        .wire{
            position: absolute;
            width: 4px;
            height: 60vh;
            background: #000;
            left: calc(50% - 2px);
            bottom: 50%;
            z-index: 1;
        }
        .button{
            position: absolute;
            bottom: 30px;
            width: 6vw;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 12px;
            right: 40px;
            height: 10vh;
            background-color: #ddd;
        }
        #btn{
            width: 1vw;
            height: 3vh;
            border-bottom: 7px solid black;
            transition: 0.2s ease;
        }
    </style>
</head>
<body>
   <div class="light">
    <div class="wire"></div>
    <div class="bulb" id="blb">
     </div>
    <div class="button">
        <button id="btn"></button> 
    </div>     
     </div>
  <script>
    var blb = document.getElementById("blb");
    var btn = document.getElementById("btn");
    var nothing = window.getComputedStyle(blb,'::before')
    console.log(nothing.position)
    var stu = 0;
    btn.addEventListener('click',function(){
    if (stu == 1) {
    blb.style.background = "#444"
    stu = 0;
    btn.style.color = "#ddd"
    blb.style.transition = "0.6s ease"
    blb.style.border = "#444"
    blb.style.boxShadow = "none"
    btn.style.borderBottom = "7px solid black"
    btn.style.borderTop = '2px solid black'
    blb.style.setProperty('--beforeback','#444')
}   else {
    blb.style.background = "yellow"
    stu = 1;
    btn.style.color = "#333"
    blb.style.transition = "0.6s ease"
    blb.style.border = "#fff"
    blb.style.boxShadow = "yellow 0px 0px 50px, yellow 0px 0px 100px, yellow 0px 0px 150px, yellow 0px 0px 200px, yellow 0px 0px 250px, yellow 0px 0px 300px, yellow 0px 0px 350px"
    btn.style.borderTop = "7px solid black"
    btn.style.borderBottom = '2px solid black'
    blb.style.setProperty('--beforeback','yellow')
}

})

  </script>
</body>
</html>
