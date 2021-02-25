<template>
    <div id="app" class="container">
        <div>
            <draggable v-model="dataList1" group="items" tag="p">
                <transition-group>
                    <div class="card" v-for="item in dataList1" :key="item.id">
                        {{ item.text }}
                    </div>
                </transition-group>
            </draggable>
        </div>
        <div>
            <draggable v-model="dataList2" group="items">
                <transition-group>
                    <div class="card2" v-for="item in dataList2" :key="item.id">
                        {{ item.text }}
                    </div>
                </transition-group>
            </draggable>
        </div>
        <div>{{ dataList1 }}</div>
        <div>{{ dataList2 }}</div>
    </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
    name: 'App',
    components: {
        draggable
    },
    data() {
        return {
            dataList1: [
                { id: 0, text: 'A' },
                { id: 1, text: 'B' },
                { id: 2, text: 'C' },
                { id: 3, text: 'D' }
            ],
            dataList2: [
                { id: 4, text: 'a' },
                { id: 6, text: 'b' },
                { id: 7, text: 'c' },
                { id: 8, text: 'd' }
            ]
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.card {
    background-color: lightpink;
    margin: 8px;
    width: 200px;
}

.card2 {
    background-color: lightseagreen;
    margin: 8px;
    width: 200px;
}
</style>
