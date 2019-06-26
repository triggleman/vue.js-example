<template>
  <div class="data">
    <!-- Pup display! Here we need to display the image of the pup that was hovered over. -->
    <!-- We can also write a conditional, IF the status key in the returned data object is false... -->
    <div
      class = "display"
      v-if="status === false ">
      <!-- Then we can display the first pup in the pups array from the returned data object-->
      <img
        v-bind:src="pups[0].source"
        class="displayImage">
    </div>

    <!-- ELSE, we can display the pup that was hovered over, which is taken from the source key in the returned data object -->
    <div class = "display" v-else>
      <img v-bind:src="source"class="displayImage">
    </div>

    <div class = "likedPups">
      <h3>Liked Pups!</h3>
      <div class="likecont">
      <span v-for="name in names"> {{name}} </span>
      </div>
    </div>
    <div class = "dogs">
      <div
        v-for="(pup, index) in pups"
        class= "pic-cont"
        v-on:mouseover="hoverPup(index)"
        v-on:click="clickPup(index)"
        >
        <img v-bind:src="pup.source" class= "pic"/>
        <h3>{{pup.title}}</h3>
      </div>
    </div>
  </div>
</template>

<!-- =====================JAVASCRIPT HERE ==================== -->
<script>
  export default {
    data() {
      return {
        pups: [{
          "title": "bully",
          "source": "https://s-media-cache-ak0.pinimg.com/736x/d2/33/9a/d2339a636c856482fd03fb3c9b045d62.jpg"
        }, {
          "title": "fluffer",
          "source": "https://s-media-cache-ak0.pinimg.com/736x/ca/32/44/ca3244addedf3b1e9fd0d90629bc339e--tea-cups-too-cute.jpg"
        }, {
          "title": "unlikely friends",
          "source": "http://funnyworldnews.com/wp-content/uploads/2016/05/0-1.jpg"
        }, {
          "title": "teacup",
          "source": "https://cdn.pixabay.com/photo/2015/02/05/12/09/chihuahua-624924_960_720.jpg"
        }, {
          "title": "ups and downs",
          "source": "http://www.lifewithdogs.tv/wp-content/uploads/2014/03/3.21.14-National-Puppy-Day5.jpg"
        }, {
          "title": "goldy",
          "source": "https://s-media-cache-ak0.pinimg.com/736x/df/0b/0d/df0b0d2a5c5700dc9beb0073c4638c29--puppy-eyes-puppy-face.jpg"
        }, {
          "title": "stuck",
          "source": "https://s-media-cache-ak0.pinimg.com/736x/a4/c4/a4/a4c4a493e5ebc7c3ae17191f00d8c916--cute-puppy-pictures-puppy-pics.jpg"
        }, {
          "title": "regal",
          "source": "https://s-media-cache-ak0.pinimg.com/originals/7e/d4/cc/7ed4ccd3e8e6a50ac4dc4abf2df0b6ba.jpg"
        }, {
          "title": "son of wolves",
          "source": "https://s-media-cache-ak0.pinimg.com/736x/5d/88/11/5d88111f799478593443356fcb49e485--dachshund-puppies-pet-puppy.jpg"
        }],
        source: "",
        names: [],
        status: false,
      }
    },
    methods: {
      hoverPup(index){
        console.log(this.pups[index].source)
        this.source = this.pups[index].source
        this.status = true
      },
      clickPup(index){
        this.names.push(this.pups[index].title)
      }
    }
  }
</script>

<!-- ===========================STYLING HERE ====================== -->
<style>
.data {
  display: flex;
  flex-direction: column;
  width: 70vw;
  margin: auto;
  align-items: center;
}
.dogs {
  width: 80vw;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;

}
.pic-cont {
  margin: 2px;
  width: 200px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  color: rgb(185, 64, 205);
  background-color: rgb(255, 167, 148);
}
.pic{
  height: 100px;
  min-width: 100px;
  background-color: rgb(255, 97, 97);
  margin: 10px;
  margin-bottom: 0px;
}
.displayImage{
  display: block;
  width: 400px;
  height: 400px;
  margin: 0 auto;
  margin-top: 50px;
}
.likedPups{
  width: 30vw;
  height: 20vh;
  background-color: rgb(163, 163, 163);
  margin: 20px;
  color: white;
  overflow: scroll;
}

.likecont {
  width: 25vw;
  margin: auto;

}

</style>
