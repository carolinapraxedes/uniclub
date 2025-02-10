<template>
    <header class="sticky-top ">
        <div class="header-line"></div>
        <div class="header-body">
            <div class="container">
                <div class="d-flex justify-content-between align-items-center py-4">
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
        <div class="header-footer ">
            <nav class="navbar container">
                <ul class="navbar-nav d-flex flex-row align-items-center">
                    <li class="nav-item ps-2">
                        <a href="" class="nav-link d-flex align-items-center" @click.prevent="toggleMenu">
                            <div>
                                <span>
                                    <img src="/src/assets/icons/menu.svg" alt="">
                                </span>
                            </div>
                            <div class="ms-2">
                                <b>Departamentos</b>
                                <span class="ms-2">
                                    <img src="/src/assets/icons/seta.svg" alt="">
                                </span>
                            </div>
                        </a>
                    </li>
                    <li class="nav-item mx-2">|</li>
                    <li class="nav-item">
                        <a href="" class="nav-link">Descontos Cliente Unimed Natal</a>
                    </li>

                    <div class="flex-grow-2"></div>

                    <!-- Item à direita -->
                    <li class="nav-item">
                        <a href="" class="nav-link">Venda no Uniclub</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
    <div class="position-relative">
        <div v-if="menuOpen" class="menu-dropdown">
            <Categoria :categories="categoryList" />
        </div>
    </div>
</template>

<script>
import Categoria from '../ui/Categoria.vue';

import HeaderInfo from './HeaderInfo.vue';
    export default {
        name: 'Header',
        data() {
            return{
                menuOpen: false,
                categoryList: [
                    {
                    title: "Saúde e Bem-estar",
                    items: ["Beleza", "Cuidados Pessoais", "Esportes e Aventura"],
                    },
                    {
                    title: "Estilo",
                    items: ["Vestuário", "Calçados", "Bijuterias e Acessórios"],
                    },
                    {
                    title: "Eletro",
                    items: ["Eletrodomésticos", "Celulares, Tablets e Acessórios", "Câmeras e Acessórios"],
                    },
                    {
                    title: "Casa",
                    items: ["Casa, Jardim e Limpeza", "Móveis e Decoração", "Construção"],
                    },
                    {
                    title: "Mais Departamentos",
                    items: ["Petshop", "Produtos Regionais", "Brinquedos e Jogos", "Livros", "Música e Hobbies", "Bebês", "Alimentos e Bebidas", "Agro e Indústria"],
                    },
                ]
            }
        },
        methods: {
            toggleMenu() {
                this.menuOpen = !this.menuOpen; // Alterna entre abrir e fechar
            }

        },
        components:{
            HeaderInfo,
            Categoria
        }
    };
</script>

<style scoped>
    .header-line{
        background-color: var(--orange);
        height: 0.5rem; /* 8px*/
    }
    .header-body{
        background-color: var(--white-tertiary);
    }
    #search{
        width: 35.75rem; /* 572px  */
        height: 3.375rem; /* 54px  */
    }

    #search-input{
        width: 100%;
        border-radius: 1.875rem; /* 30px */
        border: none;
        padding: 0.8125rem 1.25rem; /* 13px e 20px */
    }

    #search-btn{
        background-color: transparent;
        border: none;
    }
    .header-footer{
        height: 3.75rem; /* 60px */
        background-color: var(--white-secondary);
    }

    .menu-dropdown {
        position: absolute;
        top: 0px;
        left: 14%;
        width: 1198px;
        background: white;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        z-index: 1000;
    }




</style>