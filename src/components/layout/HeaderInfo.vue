<template>
    <div class="d-flex ">
        <img :src="srcIcon" :alt="altText">
        <div class="text-header-info ps-2 "style="cursor: pointer;">
            <b>
                {{title}}
            </b>
            <br>
            {{ phrase }}
        </div>

    </div>
</template>

<script>
  export default {
    name: 'HeaderInfo',
    props:{
        srcIcon: String,
        title: String,
        phrase: String,
        altText: String

    },

  };
</script>

<style scoped>
  .text-header-info{
    font-size: 16px;
    line-height: 18px;
  }

</style>