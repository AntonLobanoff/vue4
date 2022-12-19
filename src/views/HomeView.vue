<template>

  <div class="conteiner">
    <h1>Student list</h1>
    <div class="info">
      <input class="inp" type="text" placeholder="FirstName" v-model="name">
      <input class="inp" type="text" placeholder="LastName" v-model="lastNmame">
      <button class="save" @click="add">ADD</button>
      <list-content :list="list" @removeList="remove"></list-content>
    </div>
  </div>
</template>

<script>
import List from '../components/ListContent.vue'
export default {
  components: {
    'list-content': List
  },
  data() {
    return {
      name: '',
      lastNmame: '',
      list: []
    }
  },
  methods: {
    add() {
      if (this.name.length && this.lastNmame.length) {
        this.list.push(`${this.name} g${this.lastNmame}`)
        this.name = ''
        this.lastNmame = ''
      } else {
        console.log('write something')
      }
    },
    remove(index) {
      this.list.splice(index, 1)
    }
  }
}
</script>


<style>
.list {

  margin-bottom: 5px;
  line-height: 0;
  display: flex;
  justify-content: baseline;
  text-align: center;
  margin-left: 45%;

}


.conteiner {

  left: 0;
  top: 0;
  text-align: center;
  background-image: url(src/views/Background/BG.png);
  width: 100vw;
  height: 100vh;
  display: inline-block;
  vertical-align: middle;

}


.info {

  margin-top: 30px;

}


.inp {

  background-color: rgba(0, 0, 255, 0.143);
  margin-bottom: 20px;

}


.save {

  background-color: rgba(0, 0, 255, 0.143);
  border-radius: 5px;

}


.save:hover {

  background-color: blue;
  font-size: 14px;

}


.del {

  background-color: aqua;
  border-radius: 5px;
  border: none;
  margin-left: 15px;
}


.del:hover {

  background-color: red;

}
</style>

