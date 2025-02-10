<template>
    <div class="position-absolute " >
        <div class="container card  w-100 bg-white shadow">
            <div class="row m-4">
            <div v-for="(category, index) in categories" :key="index" class="col-md-2">
                <h6 class="fw-bold">{{ category.title }}</h6>
                <ul class="list-unstyled">
                <li v-for="(item, i) in category.items" :key="i">{{ item }}</li>
                </ul>
                <a href="#" class="text-orange">Ver mais ⌄</a>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    name: 'Categoria',
    props: {
        categories: {
        type: Array,
        required: true
        }
    },data(){
        return {

        }
    },

  };
</script>

<style scoped>
.text-orange {
  color: orange;
  text-decoration: none;
}
.text-orange:hover {
  text-decoration: underline;
}

</style>