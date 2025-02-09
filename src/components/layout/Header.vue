<template>
    <header class="sticky-top">
        <div class="header-line"></div>
        <div class="header-body">
            <div class="container">
                <div class="d-flex justify-content-between align-items-center p-4">
                    <a href="#">
                        <img src="/src/assets/img/logo-uniclub.webp" width="220px" height="36px" alt="Logo do Uniclub">
                    </a>
                    <div id="search">
                        <form action="" class="position-relative">
                            <input type="search" id="search-input" placeholder="O que você gostaria hoje?">
                            <button id="search-btn" class="position-absolute top-50 end-0 translate-middle-y me-2" type="submit">
                                <img  src="/src/assets/icons/lupa.svg" alt="Lupa para busca">
                            </button>
                        </form>
                    </div>
                    <HeaderInfo
                        srcIcon="/src/assets/icons/cep.svg"
                        title="Onde"
                        phrase="você está?"
                        altText="Informe seu CEP"
                    />
                    <HeaderInfo
                        srcIcon="/src/assets/icons/user.svg"
                        title="Faça login"
                        phrase="ou cadastra-se"
                        altText="Faça o login"
                    />
                    <a href="">
                        <img  src="/src/assets/icons/carrinho.svg" alt="">
                    </a>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
    import HeaderInfo from './HeaderInfo.vue';
    export default {
        name: 'Header',
        data() {

        },
        methods: {

        },
        components:{
            HeaderInfo
        }
    };
</script>

<style scoped>
    .header-line{
        background-color: var(--orange);
        height: 8px;
    }
    .header-body{
        background-color: var(--white-tertiary);
    }
    #search{
        width: 572px;
        height: 54px;
    }

    #search-input{
        width: 100%;
        border-radius: 30px;
        border: none;
        padding: 13px 20px;
    }

    #search-btn{
        background-color: transparent;
        border: none;
    }




</style>