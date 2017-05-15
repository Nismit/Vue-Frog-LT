<template>
  <div id="modal">
    <div class="modal-inner">
      <h2>Add to the list</h2>
      
      <div>
        <label>Name</label><br>
        <input type="text" placeholder="Name" name="Name" v-model="inputName" />
      </div>
      <div>  
        <label>Description</label><br>
        <input type="text" placeholder="Description" name="Description" v-model="inputDescription" />
      </div>
      <div>  
        <label>Category</label><br>
        <select v-model="selected">
          <option>English</option>
          <option>Technology</option>
          <option>Others</option>
        </select>
      </div>
      <div>  
        <label>Presentation Link</label><br>
        <input type="text" placeholder="URL" name="URL" v-model="inputURL" />
      </div>
      <div>  
        <label>SNS Link</label><br>
        <input type="text" placeholder="Twitter,Facebook,Blog" name="SNS" v-model="inputSNS" />
      </div>

      <ul>  
        <li><button @click="addToList">SUBMIT</button></li>
        <li><button @click="$emit('close')" class="cancel">CANCEL</button></li>
      </ul>  
    </div>  
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      inputName: '',
      inputDescription: '',
      selected: 'English',
      inputURL: '',
      inputSNS: ''
    }
  },
  methods: {
    addToList () {
      this.$emit('add', { name: this.inputName, description: this.inputDescription, category: this.selected, url: this.inputURL, sns: this.inputSNS })
      this.inputName = ''
      this.inputDescription = ''
      this.selected = 'English'
      this.inputURL = ''
      this.inputSNS = ''
      this.$emit('close')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #modal {
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0, .8);
    position: absolute;
    top: 0;
    left: 0;
    color: #fff;
  }

  .modal-inner {
    width: 60%;
    margin: 3em auto;
  }

  h2 {
    color: #fff;
  }

  a {
    color: #42b983;
  }

  label {
    display: inline-block;
    margin-top: 10px;
  }

  input, select {
    margin: 5px 0;
    box-sizing: border-box;
    color: #333;
  }

  input {
    width: 100%;
    padding: 2px 5px;
    font-size: 1em;
  }

  button {
    width: 100%;
    background-color: #42b983;
    border: 1px solid #42b983;
    color: #fff;
    padding: 10px 0;
    font-size: 1.2em;
    margin-top: 3em;
    cursor: pointer;
  }

  button:hover {
    background: #fff;
    color: #42b983;
  }

  button.cancel {
    background-color: #EC644B;
    border: 1px solid #EC644B;
  }

  button.cancel:hover {
    background-color: #fff;
    color: #EC644B;
  }

  ul {
    text-align: center;
  }

  li {
    display: inline-block;
    width: 40%;
  }
</style>
