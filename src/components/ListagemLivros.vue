<script setup>
import { livros } from '@/_data/livros.js'
import CardLivro from '@/components/CardLivro.vue'
</script>

<templete>
    <div class="listagem-livros">
    <card-livro v-for="livro in livro" :key="livro.id" :livro="livro" /> 
    </div>
</templete>

<style scoped>
.listagem-livros {
    display: flex;
    flex-wrap: wrap;
}
</style>