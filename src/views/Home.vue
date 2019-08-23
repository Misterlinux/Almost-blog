<template>
  <div class="home">
      <div class="container">
          <div class="nav-bar">
            <div class="headline">             
                  <p href="#"> 
                     <img class="logo" src="../assets/logo.png" />  Welcome to the Blogk
                  </p> 
              </div>                 
          </div>
        <h1 class="center">Welcome to the Blogk again</h1>

        <h2> {{ testo }} </h2>

      </div>                

     <div class="sections">
      <div v-for="(section, index) in Object.keys(entries)" :key="index" class="group">
        <h2 class="center">{{section}}</h2>
        <div class="section" v-for="entry in entries[section]" :key="entry.id">
          <div class="entry">
            <h3 @click="$router.push({name: entry.id})">
              {{entry.title}}
              <span class="subtitle">{{entry.date}}</span>
            </h3>
            <p>{{entry.description}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BLOGENTRIES from '@/statics/data/blogs.json'

export default {
  name: 'home',
  computed: {
    entries() {
      return BLOGENTRIES
    }
  },
  props: {
    testo: String
  }
}

</script>

<style lang="scss" scoped>
.center {
  text-align: center;
}
.nav-bar{
  background-color: yellow;
  height: 70px;
}

.headline {
  text-transform: uppercase;
  color: red;
  display: block;
  .logo{
    height:50px;
  }
}

h2 {
  color: #35495e;
  text-transform: capitalize;
  margin-bottom: 2rem;
}

h3 {
  color: #42b883;
  margin-bottom: 0;
  cursor: pointer;
  &:hover {
    text-decoration: underline;
  }
  .subtitle {
    color: grey;
    font-size: .98rem;
    float: right;
    font-weight: normal;
  }
}

p {
  margin-top: .4rem;
}

.sections {
  max-width: 40vw;
  margin: 0 auto;
  margin-top: 4rem;
}

.section {
  margin-bottom: 3rem;
}

.group {
  margin-bottom: 4rem;
}

</style>
