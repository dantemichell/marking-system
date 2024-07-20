<template>
    <div class="box fixed-grid is-rounded has-6-cols">
        <div class="grid">
            <div class="cell" v-for="(icon, index) in icons" :key="index">
                <component :is="icon.component" :color="icon.color" @click="cycleColor(index)" />
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import SquareIcon from "./icons/SquareIcon.vue";
import TriangleIcon from "./icons/TriangleIcon.vue";
import DiamondIcon from "./icons/DiamondIcon.vue";
import CircleIcon from "./icons/CircleIcon.vue";
import HeartIcon from "./icons/HeartIcon.vue";
import StarIcon from "./icons/StarIcon.vue";

interface Icon {
    component: any;
    color: string;
}

const colors = ['gray', 'blue', 'red'];

const icons = ref<Icon[]>([
    { component: CircleIcon, color: 'gray' },
    { component: TriangleIcon, color: 'gray' },
    { component: SquareIcon, color: 'gray' },
    { component: HeartIcon, color: 'gray' },
    { component: StarIcon, color: 'gray' },
    { component: DiamondIcon, color: 'gray' },
]);

const cycleColor = (index: number) => {
    const currentColor = icons.value[index].color;
    const nextColorIndex = (colors.indexOf(currentColor) + 1) % colors.length;
    icons.value[index].color = colors[nextColorIndex];
};
</script>
