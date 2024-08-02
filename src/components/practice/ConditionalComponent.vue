<template>
    <h1>Conditional</h1>

    <button @click="login">로그인</button>
    <br><br>
    <div v-if="isLogined">환영합니다 고갱님</div>
    <div v-else>로그인해주세여</div>
    <br><br><br>


    <h1>상품목록조회</h1>
    <ul>
        <!-- v-for에서는 반드시 key값을 지정. key값을 지정함으로써 각 요소마다의 고유식별 -->
         <!-- product는 products의 값들을 가져온다. -->
        <li v-for="product in products" :key="product.id">{{ product.name }}</li>
    </ul>

</template>


<script>

export default {
    data() {
        return {
            isLogined: false,
            products: [
                { id: 1, name: "apple" },
                { id: 2, name: "banana" },
                { id: 3, name: "strawberry" },
            ],
        }
    },
    methods: {
        login() {
            this.isLogined = true;
        }

    },
}
</script>