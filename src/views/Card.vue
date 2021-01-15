<template>
    <div class="min-w-max">
        <div class="mt-4 mb-3">
            <div class="max-w-sm teste rounded bg-white overflow-hidden shadow-lg mt-6">
                <div @click="show" class="thumb" :style="{'background': 'url('+product.imgs[0]+') 50% 50% no-repeat'}"></div>
                <div class="px-6 py-4">
                    <div class="text-gray-900 font-bold text-xl mb-0">
                        {{product.title}}
                    </div>
                    <small class="text-gray-700"> {{product.owner}} </small>
                </div>
                <div class="px-6 pt-4 pb-2">
                    <span
                        class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                        >#photography</span
                    >
                    <span
                        class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                        >#travel</span
                    >
                    <span
                        class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                        >#winter</span
                    >
                </div>
            </div>
        </div>
        <!-- all props & events -->
        <vue-easy-lightbox
            :visible="visible"
            :imgs="product.imgs"
            :index="index"
            @hide="handleHide"
        ></vue-easy-lightbox>
    </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

interface User {
    username: string;
    email: string;
    password: string;
    confirm: string;
}

export default {
    setup() {
        const user = ref({
            username: "",
            email: "",
            password: "",
            confirm: "",
        });

        const register = () => {
            const data = JSON.parse(JSON.stringify(user.value));
            console.log("Registered: ", data);
        };

        return {
            user,
            register,
        };
    },
    data() {
        return {
            imgs: "", // Img Url , string or Array of string
            visible: false,
            index: 0 // default: 0
        };
    },
    props: {
        product: {
            id: Number,
            title: String,
            imgs: [],
            owner: String
        }
    },
    methods: {
        show() {
            this.visible = true;
        },
        handleHide() {
            this.visible = false;
        },
    },
};
</script>

<style scoped>
.thumb {
    width: 100%;
    height: 230px;
    cursor: pointer;
}
.teste{
    height: 500px;;
}
</style>