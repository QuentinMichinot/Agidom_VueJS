<template>
  <div class="polaroid">
    <div class="content-polaroid">
      <div class="top"></div>
      <div class="printerin">
        <div id="s1">
          <div id="b"></div>
        </div>
      </div>
      <div class="printer"></div>
      <div class="upper">
        <div class="rainbow1"></div>
      </div>
      <div class="downer">
        <div class="rainbow"></div>
      </div>
      <div class="lense"></div>
      <button @click="addCapture()" class="button"></button>
      <div class="flash"></div>
      <div class="nod"></div>
      <div class="lable">
        <h3>Random</h3>
      </div>
    </div>
    <div id="camera" class="camera">
      <div>
        <video ref="video" id="video" width="200" height="150" autoplay></video>
      </div>
      <canvas ref="canvas" id="canvas" width="640" height="480"></canvas>
      <div>
        <input type="text" placeholder="Name" v-model="nameCapture" @keyup.enter="addCapture()">
      </div>
    </div>
    <ul class="cards">
      <li v-for="capture in captures" :key="capture" class="card-images">
        <a href="#" :title="capture.name">
          <img style="width: 200px;" :src="capture.url" alt="">
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      video: {},
      canvas: {},
      nameCapture: '',
      captures: [{
        url: '',
        name: ''
      }]
    }
  },
  mounted () {
    // this.video = this.$refs.video
    // if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
    //   navigator.mediaDevices.getUserMedia({ video: true }).then(stream => {
    //     this.video.src = window.URL.createObjectURL(stream)
    //     this.video.play()
    //   })
    // }
  },
  methods: {
    addCapture (event) {
      this.canvas = this.$refs.canvas
      var context = this.canvas.getContext('2d').drawImage(this.video, 0, 0, 640, 480)
      this.captures.push({
        url: this.canvas.toDataURL('image/png'),
        name: this.nameCapture
      })
      this.nameCapture = ''
    },
    startRandom () {

    }
  }
}
</script>

<style lang="scss">
.card-images {
  float: left;
  a {
    background: white;
    display: inline;
    float: left;
    margin: 0 15px 30px 30px;
    padding: 10px 10px 25px;
    text-align: center;
    text-decoration: none;
    -webkit-box-shadow: 0 4px 6px rgba(0, 0, 0, .3);
    -moz-box-shadow: 0 4px 6px rgba(0,0,0,.3);
    box-shadow: 0 4px 6px rgba(0,0,0,.3);
    -webkit-transition: all .15s linear;
    -moz-transition: all .15s linear;
    transition: all .15s linear;
    z-index:0;
    position:relative;

    // &:before {
    //   content: url('../../assets/punaise.png');
    //   position: absolute;
    //   z-index: 2;
    //   top: -25px;
    //   left: 55%;
    //   -webkit-transform: translateX(-50%);
    //   transform: translateX(-50%);
    // }
    &:after {
      color: #333;
      font-size: 20px;
      content: attr(title);
      position: absolute;
      bottom: 3px;
      left: 50%;
      transform: translateX(-50%);
    }
    &:nth-child(2n) {
      -webkit-transform: rotate(4deg);
      -moz-transform: rotate(4deg);
      transform: rotate(4deg);
    }
    &:nth-child(3n) {
      -webkit-transform: rotate(-24deg);
      -moz-transform: rotate(-24deg);
      transform: rotate(-24deg);
    }
    &:hover{
      -webkit-transform: rotate(0deg);
      -moz-transform: rotate(0deg);
      transform: rotate(0deg);
      -webkit-transform: scale(1.2);
      -moz-transform: scale(1.2);
      transform: scale(1.2);
      z-index:10;
      -webkit-box-shadow: 0 10px 20px rgba(0, 0, 0, .7);
      -moz-box-shadow: 0 10px 20px rgba(0,0,0,.7);
      box-shadow: 0 10px 20px rgba(0,0,0,.7);
    }
  }
  .img {
    display: block;
    width: inherit;
  }
}

.camera {
  position: absolute;
  left: 405px;
  input {
    padding: 10px;
    margin-top: -5px;
  }
}
#video {
  background-color: #000000;
  border: 5px solid white;
}
#canvas {
  display: none;
}
.polaroid {
  top:100px;
  width:100%;
  text-align:center;
  perspective:100px;
  margin-bottom:300px;
}
.content-polaroid {
  left: 15px;
  position: absolute;
}
.upper {
  position:absolute;
  left:40px;
  width:350px;
  height:150px;
  border-radius:20px 20px 0px 0px;
  background:white;
}
.downer {
  position:absolute;
  top:150px;
  left:25.5px;
  width:355px;
  height:60px;
  border-radius:0px 0px 0px 0px;
  background: linear-gradient(rgb(240,240,240), white);
  tarnsform-style:preserve-3d;
  transform:rotatex(3deg);
  perspective:100px;
}
.printer {
  position:absolute;
  top:213px;
  left:10px;
  width:362px;
  height:35px;
  background:rgb(30,30,30);
  &:after {
    content:"";
    position:absolute;
    top:20px;
    left:40px;
    width:280px;
    height:15px;
    border-radius:10px 10px 0px 0px;
    background:rgb(50,50,50);
  }
}
.printerin {
  position:absolute;
  top:248px;
  left:10px;
  width:362px;
  height:35px;
  border-radius:0px 0px 20px 20px;
  background:rgb(30,30,30);
  &:before {
    content:"";
    position:absolute;
    top:0px;
    left:40px;
    width:280px;
    height:15px;
    border-radius:0px 0px 10px 10px;
    background:rgb(50,50,50);
  }
}
.rainbow2 {
  position:absolute;
  top:-20px;
  left:157px;
  height:20px;
  width:50px;
  background-image: repeating-linear-gradient(to right,
  #EF0079 0px, #EF0079 10px,
  #D70006 10px, #D70006 18px,
  #FF9C00 18px, #FF9C00 26px,
  #FEEB00 26px, #FEEB00 34px,
  #5DB333 34px, #5DB333 42px,
  #00B2FF 42px, #00B2FF 50px);
  opacity:.7;
}
.lense {
  position:absolute;
  top:31px;
  left:160px;
  width:100px;
  height:100px;
  border-radius:50%;
  background:black;
  border:4px solid rgb(50,50,50);
  box-shadow:-10px 10px 30px rgb(50,50,50);
  &:after {
    content:"";
    position:absolute;
    left:10px;
    top:25px;
    width:20px;
    height:20px;
    border-radius:50%;
    background:white;
  }
  &:before {
    content:"";
    position:absolute;
    left:20px;
    top:20px;
    width:50px;
    height:50px;
    border-radius:50%;
    background:white;
    opacity:.5;
  }
}
.button {
  position:absolute;
  left:60px;
  top:90px;
  width:50px;
  height:50px;
  border-radius:50%;
  background:#FF0200;
  border:3px solid rgb(230,230,230);
  cursor:pointer;
  box-shadow:0px 0px 5px black;
  outline: none;
  &:focus {
    position:absolute;
    left:60px;
    top:90px;
    width:50px;
    height:50px;
    border-radius:50%;
    background:#C62828;
    border:3px solid rgb(230,230,230);
    cursor:pointer;
    box-shadow:0px 0px 5px black;
    outline: none;
  }
}
.flash {
  position:absolute;
  left:290px;
  top:30px;
  width:70px;
  height:50px;
  background: repeating-linear-gradient(
  to right,
  grey,
  grey 10px,
  rgb(50,50,50) 10px,
  rgb(50,50,50) 20px
  );
  border:solid;
}
.nod {
  position:absolute;
  left:305px;
  top:96px;
  width:25px;
  height:25px;
  border-radius:50%;
  background:rgb(20,20,20);
  border:5px solid rgb(50,50,50);
}
.lable {
  position:absolute;
  left:55px;
  top:30px;
  width:90px;
  height:40px;
  background:rgb(30,30,30);
  border-radius:10px 10px 10px 10px;
  text-align:center;
  h3 {
    position:absolute;
    top:-10px;
    left:10px;
    color:white;
    font-family: 'Roboto', sans-serif;
  }
}
.rainbow1 {
  opacity:.8;
  position:absolute;
  top:50px;
  left:153px;
  height:130px;
  width:48px;
  background-image: repeating-linear-gradient(to right,
  #EF0079 0px, #EF0079 8px,
  #D70006 8px, #D70006 16px,
  #FF9C00 16px, #FF9C00 24px,
  #FEEB00 24px, #FEEB00 32px,
  #5DB333 32px, #5DB333 40px,
  #00B2FF 40px, #00B2FF 48px);
}
.rainbow {
  position:absolute;
  top:-2px;
  left:155px;
  height:61px;
  width:48px;
  background-image: repeating-linear-gradient(to right,
  #EF0079 0px, #EF0079 8px,
  #D70006 8px, #D70006 16px,
  #FF9C00 16px, #FF9C00 24px,
  #FEEB00 24px, #FEEB00 32px,
  #5DB333 32px, #5DB333 40px,
  #00B2FF 40px, #00B2FF 48px);
    tarnsform-style:preserve-3d;
  transform:rotatex(10deg);
}
#s1 {
  position:absolute;
  top:-240px;
  left:60px;
  width:230px;
  height:180px;
  border:5px solid white;
  border-bottom:30px solid white;
  box-shadow:0px 0px 40px black;
  background: url('https://cdni.rbth.com/rbthmedia/images/all/2017/05/28/russia_selfie.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  transition:.5s;
  transfrom-origin:top;
}
#b {
  position:absolute;
  top:0px;
  left:0px;
  width:230px;
  height:180px;
  background:black;
  transition:.5s;
  transfrom-origin:top;
}
.top {
  position:absolute;
  top:-10px;
  left:90px;
  background:rgb(40,40,40);
  width:250px;
  height:20px;
  border-radius:10px 10px 0px 0px;
}
@keyframes print {
  0% {
  top:-240px;
    background:rgb(0,0,0);
  }
  10% {
  top:-200px;
    background:rgb(0,0,0);
  }
  20% {
  top:-150px;
    background:rgb(0,0,0);
  }
  30% {
  top:-100px;
    background:rgb(0,0,0);
  }
  40% {
  top:-50px;
    background:rgb(0,0,0);
  }
  50% {
  top:-10px; background:rgb(0,0,0);
  }
  60% {
  top:0px; background:rgb(0,0,0);
  }
  100% {
    top:60px;background:rgb(0,0,0);
  }
}
@keyframes show {
  from {
    opacity:1;
  }
  to {
    opacity:0;
  }
}
</style>
