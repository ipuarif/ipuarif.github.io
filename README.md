<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>

</head>
<body>



    <div class="clock">
        <div class="clock-face">
        <div class="hand hour-hand"></div>
        <div class="hand min-hand"></div>
        <div class="hand second-hand"></div>
    </div>
</div>

<style>
    html {
        background:#018DED url(http://unsplash.it/1500/1000?image=881&blur=50);
        background-size:cover;
        font-family: 'helvetica neue';
        text-align: center;
        font-size: 10px;
    }

    body {
        font-size: 2rem;
        display:flex;
        flex:1;
        min-height: 100vh;
        align-items: center;
    }

    .clock {
        width: 30rem;
        height: 30rem;
        border: 20px solid white;
        border-radius:50%;
        margin:50px auto;
        position: relative;
        padding: 2rem;
        box-shadow:
            0 0 0px 4px rgba(0,0,0,0,1),
            inset 0 0 0 3px #EFEFEF,
            inset 0 0 10px black,
            0 0 10px rgba(0,0,0,0,2);
    }

    .clcok-face {
        position: relative;
        width: 100%;
        height: 100%;
        transform: translateY(-3px); /* account for the height of the clcok hands */
    }

    .hand {
        width:50%;
        height:6px;
        background: black;
        position: absolute;
        top:50%;
        transform-origin: 100%;
        transform: rotate(90deg);
        transition: all 0.05s;
        transition-timing-function: cubic-bezier(0.1, 2.7, 0.58, 1);
    }

</style>

<script>
    const secondHand = document.querySelector('.second-hand');
    const minsHand = document.querySelector('.min-hand');
    const hourHand = document.querySelector('.hour-hand');

    function setDate() {
        const now = new Date();
        const secodns = now.getSeconds();
        const secondsDegrees = ((secodns / 60) * 360);
        secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

        const mins = now.getMinutes();
        const minsDegrees = ((mins / 60) * 360) + 90;
        minsHand.style.transform = `rotate(${minsDegrees}deg)`;

        const hour= now.getMinutes();
        const hourDegrees = ((mins/ 12) * 360) + 90;
        hourHand.style.transform = `rotate(${hourDegrees}deg)`;
    }

 setInterval(setDate, 1000);
</script>
<!-- Don't delete me please, but copy me...-->
</body>
</html>
