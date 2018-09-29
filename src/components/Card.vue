<template>
  <div class="card">
    <h1>{{ title }}</h1>
    <div class="polaroid-images">
      <a href="" title="Quentin">
        <img height="200" src="https://raw.githubusercontent.com/Ashwinvalento/cartoon-avatar/master/lib/images/male/45.png" alt="Quentin" title="Quentin" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  data () {
    return {
      title: 'Agidom'
    }
  }
}
</script>

<style lang="scss" scoped>
  .polaroid-images {
    a {
      background: white;
      display: inline;
      float: left;
      margin: 0 15px 30px;
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

</style>
