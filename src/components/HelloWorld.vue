<template>
  <div class="hello">
    <input v-model="name" placeholder="What are you thankful for?">
    <h1>Today I'm thankful for</h1>
    <h1 class="thankful_msg">{{name}}</h1>

    <button @click="addMessage" class="add_button">Add To happyfeels Wall</button>

    <br><br>

    <button v-on:click="greet(greeting)" type="button" name="button" class="surprise_button">Click Me For A Surprise!</button>
    <br><br>
    <hr>
    <br>
    <h3>Things We're Thankful For:</h3>
    <div class="messages">
      <span v-for="message in messages">
          {{message.name}}<br><br>
      </span>
    </div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      counter: 0,
      name: '',
      messages: [],
      message: '',
      greeting: 'You look wonderful today :)'
    }
  },

  methods: {
    addMessage() {
      const message = {
          name: this.name, //name here
      }
      this.counter++;
      this.messages.push(message)
      this.name='';
    },

    greet: function(greeting) {
      alert(greeting);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
a {
  color: #42b983;
}
.hello {
  margin: 50px;
  padding: 20px;
}

.thankful_msg {
  text-decoration: underline;
}

.add_button {
  padding: 10px;
  border-radius: 10px;
  font-size: 12px;
  color: white;
  background-color: #ff6699;
}

.surprise_button {
  padding: 20px;
  border-radius: 30px;
  font-size: 12px;
  color: white;
  background-color: #3366ff;
}

.messages {
  margin: 50px;
}
</style>
