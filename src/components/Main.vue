<template>
  <div class="section" style="backgroundColor:#223334;">
  <div class="title has-text-white">EmojiType</div>
  <div class="section" style="color:white;backgroundColor:#223334;outline:none;border:none;width:100%;" v-on:keyup="type">
  {{data}}
  </div>
  </div>
</template>

<script>
export default {
  name: 'Main',
  data () {
    return {
      emoji: "",
      data: ""
    }
  },
  methods: {
    type: function(e){
      this.data += ""
    }
  },
  created(){
    let el = this;
    window.addEventListener('keyup', function(){
      el.data += el.emoji[Math.floor(Math.random() * el.emoji.length)].split(" ")[0];
      el.data += el.emoji[Math.floor(Math.random() * el.emoji.length)].split(" ")[0];
      el.data += el.emoji[Math.floor(Math.random() * el.emoji.length)].split(" ")[0];
      if(Math.floor(Math.random() * 100) < 20){
        el.data += " "
      }
    })
  },
  mounted () {
    let el = this;
    fetch('https://gist.githubusercontent.com/endolith/157796/raw/a37a313160a2e9d9de8d7c8151ddb9b3cc250e0d/Unicode%2520official%2520emojis.txt').then(response => {
      return (response.text())
    }).then (response => {
      el.emoji = response.split("\n");
    });

  }
}
</script>
