<script setup>
import {
  carrinho,
  removerItemCarrinho,
  atualizaQuantidadeItem,
  limparCarrinho
} from '@/_data/carrinho.js'
import MButton from './MButton.vue'
import carrinhoVazio from './carrinhoVazio.vue'


function formatarPreco(preco) {
  return 'R$' + preco.toFixed(2).replace('.', '.')
}
</script>

<template>
    <div class="carrinho">
        <h2>Meu Carrinho</h2>
        <div class="wrap-carrinho">
            <m-message v-if="carrinho.itens.length === 0" />
            <div v-else>
                <div class="item-carrinho" v-for="(item, index) in carrinho.itens" :key="index">
                <div class="info-livro">
                    <div class="imagem-livro">
                        <img src="item.img" class="icon-capa-livro"/>
                    </div>
                    .
                </div>
                </div>
            </div>
        </div>
    </div>
</template>