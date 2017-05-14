<template>
  <div class="lists">
    <button @click="showModal = true">+</button>

    <modal v-if="showModal" @add="addList" @close="showModal = false"></modal>

    <cards :lists="lists"></cards>

  </div>
</template>

<script>
import Cards from './Cards'
import Modal from './Modal'
export default {
  data () {
    return {
      showModal: false,
      lists: [
        { name: 'John Doe', description: 'Test Description', category: 'English', url: 'http://www.google.ca', sns: 'Github: @nismit' },
        { name: 'hoge', description: '日本語ディスクリプションテスト日本語ディスクリプションテスト', category: 'English', url: 'http://www.google.ca', sns: 'Github: @hoge' },
        { name: 'hage', description: 'Test Description', category: 'Technology', url: 'http://www.google.ca', sns: 'Twitter: @hage' }
      ]
    }
  },
  components: {
    Cards,
    Modal
  },
  methods: {
    addList (elem) {
      this.lists.push(elem)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  input {
    padding: 5px 10px;
    font-size: .8rem;
  }

  button {
    position: fixed;
    bottom: 50px;
    right: 50px;
    border: 1px solid #ddd;
    border-radius: 50%;
    background: #ff3466;
    color: #fff;
    cursor: pointer;
    width: 42px;
    height: 42px;
    font-size: 1.5em;
  }

</style>
