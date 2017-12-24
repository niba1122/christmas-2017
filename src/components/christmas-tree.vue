<template>
    <svg>
            <!-- :initial-x="50 + Math.floor(i / 10) * 50"
            :initial-y="50 + (i % 10) * 50" -->
        <draggable-item 
            v-for="(item, i) in items"
            :src="item.imagePath"
            :key="i"
            :initial-x="500 + Math.random() * 500"
            :initial-y="Math.random() * 500"
            width="30"
            height="50" />
    </svg>
</template>
<script>

import DraggableItem from './draggable-item'

class Item {
    constructor(name) {
        this.name = name
        this.isSelected = false;
    }

    get imagePath() {
        return `http://nobuhito.ibaraki.jp/christmas-tree-icons/${this.name}.png`
    }
}

export default {
    data() {
        return {
            items: [
                new Item('bag'),
                new Item('bell'),
                new Item('candle'),
                new Item('candy'),
                new Item('christmas-tree'),
                new Item('cottage'),
                new Item('crystal-ball'),
                new Item('fireplace'),
                new Item('gift'),
                new Item('glove'),
                new Item('hat'),
                new Item('lampion-1'),
                new Item('lampion-2'),
                new Item('moose'),
                new Item('ornament'),
                new Item('santa'),
                new Item('sledge'),
                new Item('snowflake-1'),
                new Item('snowflake-2'),
                new Item('snowflake-3'),
                new Item('snowflake-4'),
                new Item('snowflake-5'),
                new Item('snowman'),
                new Item('sock'),
                new Item('star')
            ]
        }
    },
    components: {
        'draggable-item': DraggableItem
    },
}
</script>