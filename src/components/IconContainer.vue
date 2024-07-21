<template>
    <div class="columns is-vcentered p-2">
        <div class="column"></div>
        <div class="column is-7">
            <div class="box fixed-grid is-rounded has-6-cols">
                <div class="grid">
                    <div class="cell" v-for="(icon, index) in icons" :key="index">
                        <component :is="icon.component" :color="getColor(icon.color)" @click="cycleColor(index)" />
                    </div>
                </div>
            </div>
            <div class="row">
                <span v-for="(icon, index) in icons" :key="index">{{ getColor(icon.color) }}</span>
            </div>
            <div class="row is-family-monospace">
                <span>DMS{{ getColorIndexes().join('') }}</span>
            </div>
        </div>
        <div class="column"></div>
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

enum Color {
    GRAY = 'gray',
    BLUE = 'blue',
    RED = 'red'
}

interface Icon {
    component: any;
    color: Color;
}

const colors = [Color.GRAY, Color.BLUE, Color.RED];

const icons = ref<Icon[]>(assignIcons());

function assignIcons(): Icon[] {
    return [
        { component: CircleIcon, color: Color.GRAY },
        { component: TriangleIcon, color: Color.GRAY },
        { component: SquareIcon, color: Color.GRAY },
        { component: HeartIcon, color: Color.GRAY },
        { component: StarIcon, color: Color.GRAY },
        { component: DiamondIcon, color: Color.GRAY }
    ];
}

const cycleColor = (index: number) => {
    const currentColor = icons.value[index].color;
    const nextColorIndex = (colors.indexOf(currentColor) + 1) % colors.length;
    icons.value[index].color = colors[nextColorIndex];
};

const getColor = (color: Color): string => {
    return color;
};

// Función para obtener los valores de color de todos los íconos
const getIconColors = (): string[] => {
    return icons.value.map(icon => icon.color);
};

// Función para establecer los valores de color de los íconos desde un array
const setIconColors = (colorArray: string[]) => {
    colorArray.forEach((color, index) => {
        if (colors.includes(color as Color) && icons.value[index]) {
            icons.value[index].color = color as Color;
        }
    });
};

// Función para obtener un array de los índices de los colores
const getColorIndexes = (): number[] => {
    return icons.value.map(icon => colors.indexOf(icon.color));
};

// Función para establecer los colores desde un array de índices
const setColorIndexes = (indexArray: number[]) => {
    indexArray.forEach((colorIndex, index) => {
        if (colorIndex >= 0 && colorIndex < colors.length && icons.value[index]) {
            icons.value[index].color = colors[colorIndex];
        }
    });
};

// Ejemplo de uso de las funciones para obtener y establecer colores
// console.log(getIconColors()); // Obtiene el array de colores actuales
// setIconColors(['red', 'blue', 'gray', 'gray', 'blue', 'red']); // Establece los colores desde un array
</script>