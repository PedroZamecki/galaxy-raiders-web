<template>
    <div class="background">
        <h1 class="header">
            Leader Board
        </h1>
        <div class="leaderBoard">
            <div class="lbItem lbHeaders">
                <span>Name</span>
                <span>Score</span>
                <span>Time</span>
            </div>
            <div class="lbItem playerItem" v-for="player in players_mock" :key="player.id">
                <span>{{ player.name }}</span>
                <span>{{ player.score }}</span>
                <span>{{ player.time }}</span>
            </div>
        </div>
        <div class="buttons">
            <button class="button" @click="$router.push(`/`)">Back</button>
        </div>
    </div>
</template>

<style>
.header {
    font-size: 5rem;
    text-align: center;
    animation: rainbow 4s linear infinite;
    font-family: 'Courier New', Courier, monospace;
}

.buttons {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}

.button {
    margin: 1rem;
    padding: 1rem;
    font-size: 2rem;
    cursor: pointer;
    color: #f5f5f5;
    border-radius: 1rem;
    background-color: #36bbf5;
    border: 0.2rem solid #36bbf5;
    transition: all 0.2s ease-in-out;
    font-family: 'Courier New', Courier, monospace;
}

.button:hover {
    color: #36bbf5;
    background-color: #f5f5f5;
    border: 0.2rem solid #f5f5f5;
}

.leaderBoard {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
}

.lbHeaders {
    color: #36bbf5;
    background-color: #f5f5f5;
    border: 0.2rem solid #f5f5f5;
}

.lbItem {
    width: 150%;
    height: 100%;
    margin: 1rem;
    display: flex;
    padding: 1rem;
    font-size: medium;
    border-radius: 1rem;
    flex-direction: row;
    align-items: center;
    justify-content: space-around;
    transition: all 0.2s ease-in-out;
    font-family: 'Courier New', Courier, monospace;
}

.playerItem {
    color: #f5f5f5;
    background-color: #36bbf5;
    border: 0.2rem solid #36bbf5;
}
</style>

<script setup>
const {
    data: players,
} = await $get("/players");

// Mock Values!
const players_mock = [
    {
        name: "Player 1",
        score: 100,
        time: 100
    },
    {
        name: "Player 2",
        score: 50,
        time: 50
    },
    {
        name: "Player 3",
        score: 10,
        time: 10
    }
]
</script>