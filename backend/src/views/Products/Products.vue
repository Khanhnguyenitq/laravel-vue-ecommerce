<template>
    <div class="flex items-center justify-between mb-3">
        <h1 class="text-3xl font-semibold">Products</h1>
        <button
            type="submit"
            @click="showAddNewModal()"
            class="py-2 px-4 border border-transparent text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
            Add new Product
        </button>
    </div>
    <ProductsTable @clickEdit="editProduct" />
    <AddNewProduct
        v-model="showProductModal"
        :product="productModel"
        @close="onModalClose"
    />
</template>

<script setup>
import { ref } from "vue";
import store from "../../store";
import AddNewProduct from "./AddNewProduct.vue";
import ProductsTable from "./ProductsTable.vue";

const DEFAULT_PRODUCT = {
    id: "",
    title: "",
    description: "",
    image: "",
    price: "",
};

const productModel = ref({ ...DEFAULT_PRODUCT });

const showProductModal = ref(false);

function showAddNewModal() {
    showProductModal.value = true;
}

function editProduct(p) {
    store.dispatch("getProduct", p.id).then(({ data }) => {
        productModel.value = data;
        showAddNewModal();
    });
}

function onModalClose() {
    productModel.value = { ...DEFAULT_PRODUCT };
}
</script>
