<template>
  <div id="app">
    <link href="https://fonts.googleapis.com/css?family=Indie+Flower&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <header>
      <div class="title">
        <h1>{{ title }}</h1>
      </div>
    </header>

    <main>

      <div class="cp-carrousel">
        <b-carousel id="carousel-fade" style="text-shadow: 0px 0px 2px #000" fade indicators img-width=1024 img-height=480>
          <b-carousel-slide caption="1" :img-src="require('./images/1.png')"/>
          <b-carousel-slide caption="2" :img-src="require('./images/2.png')"/>
          <b-carousel-slide caption="3" :img-src="require('./images/3.png')"/>
          <b-carousel-slide caption="4" :img-src="require('./images/4.png')"/>
          <b-carousel-slide caption="5" :img-src="require('./images/5.png')"/>
          <b-carousel-slide caption="6" :img-src="require('./images/6.png')"/>
          <b-carousel-slide caption="7" :img-src="require('./images/7.png')"/>
          <b-carousel-slide caption="8" :img-src="require('./images/8.png')"/>
          <b-carousel-slide caption="9" :img-src="require('./images/9.png')"/>
          <b-carousel-slide caption="10" :img-src="require('./images/10.png')"/>
          <b-carousel-slide caption="11" :img-src="require('./images/11.png')"/>
          <b-carousel-slide caption="12" :img-src="require('./images/12.png')"/>
        </b-carousel>
      </div>
      
    </main>

    <footer>
      <a class="cp-contact whatsapp text-nowrap" href="https://wa.me/5511997862895" target="_blank">(11) 99786 2895 <i class="fa fa-whatsapp"></i></a>
      <a class="cp-contact gmail text-nowrap">rosanapolito@gmail.com <i class="fa fa-google"></i></a>
    </footer>

    <nav class="left">
      <div v-for="service in services" :key="service.titile">
        <Card :service="service"/>
      </div>
    </nav>

    <nav class="right">
    </nav>

  </div>
</template>

<script>
  import Card from './components/Card'
  
  export default {
    name: 'app',
    components: {
      Card
    },
    data() {
      return {
        title: 'Rosana, passeios e cuidados de pets.',
        message: '',
        showMessage: false,
        preventShow: true,
        services : [
          {
            titile: 'Pet Sitter',
            description: 'Vai viajar e não tem com quem deixar o seu bichinho? ' +
              'Agora você pode contar com o serviço de Pet Sitter',
              img: require('./images/pet-sitter.jpeg')
          },
          {
            titile: 'Dog Walker',
            description: 'Lhe falta tempo para passear com o seu cãozinho?' +
              'Agora você pode contar com serviço de Dog Walker',
            img: require('./images/dog-walker.jpeg')
          },
          {
            titile: 'Cuidados',
            description: 'Amor, carinho, companhia, passeios e cuidados em geral para seu animalzinho de estimação.',
            img: require('./images/cuidados.jpeg')
          }
        ]
      }
    },
    created() {
      // document.title = 'ROSANA PET'
    }
  }
</script>

<style scoped>

  #app {
    background: rgb(2,0,36);
    background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(145,145,209,0.11948529411764708) 27%, rgba(0,212,255,1) 100%);
  }

  .cp-carrousel{
    max-width: 600px;
    margin: 40px 40px;
    height: 400px;
  }

  .cp-contact {
    margin: 20px 50px;
    border-radius: 10px;
    width: 250px;
    display: block;
    text-align: center;
    line-height: 60px;
  }

  .whatsapp {
    background: #25d366;
  }
  
  .gmail {
    background: indianred;
  }

  p {
    font-size: 2em;
    text-align: center;
  }

  header {
    grid-area: grid-header;
  }

  nav.left {
    grid-area: grid-nav-left;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  nav.right {
    grid-area: grid-nav-right;
  }

  main {
    grid-area: grid-main;
    color: #FFF;
    display: flex;
    justify-content: center;
    position: relative;
  }

  header div.title {
    display: flex;
    justify-content: center;
    margin: 50px 10px 50px 10px;
    font-family: 'Indie Flower', cursive;
  }

  footer {
    grid-area: grid-footer;
    background: #343a40;
    display: flex;
    justify-content: center;
  }

  #app {
    display: grid;
    min-height: 100vh;
    grid-template-columns: 250px auto 250px;
    grid-template-rows: 120px 1fr 100px;
    grid-template-areas:
            'grid-header grid-header grid-header'
            'grid-nav-left grid-main grid-nav-right'
            'grid-footer grid-footer grid-footer';
    /*overflow-x: hidden;*/
  }

  @media (max-width: 950px) {
    #app {
      display: grid;
      width: 100%;
      grid-template-columns: 100%;
      grid-template-rows: 15% 1fr 1fr 5%;
      grid-template-areas:
          'grid-header'
          'grid-main'
          'grid-nav-left'
          'grid-footer';
      /*overflow-x: hidden;*/
    }
    .cp-carrousel{
      margin: 80px 80px;
    }
    header div.title {
      display: flex;
      justify-content: center;
      margin: 50px 50px 50px 50px;
      font-family: 'Indie Flower', cursive;
    }
  
    .cp-contact {
      margin: 5px 5px;
      width: auto;
    }
  
  }


</style>
