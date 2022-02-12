<template>
    <li class="catalog__item">
        <router-link :to="{name: 'product', params: {id: product.id}}" class="catalog__pic">
            <img :src="product.image" alt="Название товара">
        </router-link>

        <h3 class="catalog__title">
        <a href="#">
            {{ product.title }}
        </a>
        </h3>

        <span class="catalog__price">
        {{ product.price }} ₽
        </span>

        <ul class="colors colors--black">
            <li class="colors__item" v-for="color in product.colors" :key="color.color.id">
                <label class="colors__label">
                <input class="colors__radio sr-only" type="radio" name="color-1" :value="color.color.code" checked="">
                <span class="colors__value" :style="'background-color:' + color.color.code">
                </span>
                </label>
            </li>
        </ul>
    </li>
</template>

<script>
    export default {
        props: ['product']
    }
</script>