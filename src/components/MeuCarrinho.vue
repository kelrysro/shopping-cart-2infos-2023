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
    <h2>Meu carrinho</h2>

    <div class="wrap-carrinho">
      <carrinho-vazio v-if="carrinho.itens.length === 0" />

      <div v-else>
        <div class="item-carrinho" v-for="(item, index) in carrinho.itens" :key="index">
          <div class="info-livro">
            <div class="imagem-livro">
              <img :src="item.img" class="icon-capa-livro" />
            </div>
            <div class="detalhes-livro">
              <div>
                <p>{{ item.title }}</p>
                <p class="info-livro-preco">{{ formatarPreco(item.price) }}/un</p>
              </div>
              <div>
                <p>
                  qtde:
                  <input
                    type="number"
                    v-model="item.quantidade"
                    @change="atualizaQuantidadeItem(item)"
                    min="1"
                  />
                </p>
                <button @click="removerItemCarrinho(item)">&#128465;</button>
                <p>total:{{ formatarPreco(item.total) }}</p>
              </div>
            </div>
          </div>
        </div>
        <m-button @click="limparCarrinho()" text="Limpar carrinho" />

       
    <button type="button" class="btn btn-primary p-3 mt-2 " data-bs-toggle="modal" data-bs-target="#exampleModal">
      Finalizar compra
    </button>
    <hr>
    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Seus dados</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
          <form>
            <div>
          <h4>Informe seu nome:</h4>
          <input type="text" class="input-balao-up" v-model="nome" v-on:keypress="enviar = false" placeholder="Digite seu nome..." required />

        </div>
          </form>
          </div>
          <div class="modal-footer">
            <button @click="limparCarrinho" type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
            <button @click="limparCarrinho" type="button" class="btn btn-warning" data-bs-dismiss="modal">concluido</button>
          </div>
        </div>
      </div>
    </div>
        
        <!-- 1 -->
        </div>
    </div>
</div>

</template>

<style scoped>

.wrap-carrinho .carrinho-total {
  position: fixed;
  bottom: 3%;
  font-size: 1.5rem;
  font-weight: bold;
}
.item-carrinho .info-livro {
  display: flex;
  margin-bottom: 10px;
}

.detalhes-livro {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.detalhes-livro p {
  margin: 0;
}

.detalhes-livro div {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.detalhes-livro input[type='number'] {
  width: 50px;
  text-align: center;
  border: none;
  border-bottom: 1px solid black;
  background-color: transparent;
  margin-left: 10px;
}

.detalhes-livro button {
  background-color: transparent;
  border: none;
  cursor: pointer;
  font-size: 1.5rem;
  color: black;
  padding: 0;
  margin: 0;
}

.info-livro-preco {
  margin-left: auto;
}

.icon-capa-livro {
  width: 30px;
  margin-right: 10px;
}
</style>