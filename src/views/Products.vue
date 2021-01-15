<template>
    <div>
        <div class="place-items-center content-center grid grid-cols-1 gap-5 md:grid-cols-3 sm:grid-cols-2 lg:grid-cols-4 xl:grid-cols-5">
            <card v-for="product in products" :key="product.id" :product="product"></card>
        </div>
    </div>
</template>

<script>
// If VueApp is already registered with VueEasyLightbox, there is no need to register it here.
import VueEasyLightbox from "vue-easy-lightbox";
import Card from "./Card.vue";
export default {
    components: {
        VueEasyLightbox,
        Card,
    },
    data() {
        return {
            products: [
                {
                    id: 0,
                    title: "Verde Ubatuba",
                    owner: "João dos Granitos",
                    imgs: [
                        "https://images.unsplash.com/photo-1595871213029-7476de0d71dd?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=3322&q=80",
                        "https://images.unsplash.com/photo-1603323978104-4c1c0d1bfc72?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=2700&q=80",
                    ],
                },
                {
                    id: 1,
                    title: "Preto São Gabriel",
                    owner: "João dos Granitos",
                    imgs: [
                        "https://images.unsplash.com/photo-1539141278536-63a0f98360a7?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=2700&q=80",
                        "https://images.unsplash.com/photo-1550053808-52a75a05955d?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=1234&q=80",
                    ],
                },
            ],
        };
    },
};
</script>