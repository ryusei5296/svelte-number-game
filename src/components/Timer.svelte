<script>
    export let gameOver = false;
    export let gameClear = false;
    const startTime = new Date();
    let countTime = startTime;
    let nowTime;

    let timer = setInterval(() => {
        if (gameOver || gameClear) clearInterval(timer);
        nowTime = new Date();
        countTime = (nowTime - startTime);
    }, 10);
</script>

<h1>{countTime}</h1>