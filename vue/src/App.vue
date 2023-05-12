<script>
export default {
  name: 'App',
  data: () => {
    return {
      page: 'Item Shop',
      battleBus: [],
      skins: [
        {
          name: 'Renegade Raider',
          cost: '1200',
          image:
            'https://fortniteskins.net/wp-content/uploads/2021/11/renegade-raider-outfit-hd.png'
        },
        {
          name: 'Skull Trooper',
          cost: '1500',
          image: 'https://media.comicbook.com/2018/10/fortnite-1136633.jpeg'
        },
        {
          name: 'John Wick',
          cost: '2000',
          image:
            'https://progameguides.com/wp-content/uploads/2019/05/fortnite-outfit-john-wick.jpg?fit=875%2C915'
        },
        {
          name: 'Naruto',
          cost: '2000',
          image:
            'https://progameguides.com/wp-content/uploads/2021/11/fortnite-outfit-naruto-uzumaki-768x803.jpg'
        },
        {
          name: 'Thanos',
          cost: '2000',
          image:
            'https://progameguides.com/wp-content/uploads/2021/06/fortnite-outfit-Thanos.jpg?fit=875%2C915'
        },
        {
          name: 'Tomato Head',
          cost: '1500',
          image:
            'https://progameguides.com/wp-content/uploads/2018/08/fortnite-outfit-tomatohead.jpg?fit=875%2C915'
        }
      ]
    }
  },
  methods: {
    addSkin(skin) {
      this.battleBus.push(skin)
    },
    removeSkin(skin) {
      this.battleBus.splice(this.battleBus.indexOf(skin))
    },
    navigateTo(page) {
      this.page = page
    }
  },
  components: {}
}
</script>

<template>
  <div>
    <header>
      {{ battleBus.length }} on board
      <button v-on:click="navigateTo('bus')">View Bus</button>
      <button v-on:click="navigateTo('Item Shop')">View Item Shop</button>
    </header>
    <div v-if="page === 'bus'">
      <h1>Bus</h1>
      <div class="skins">
        <div v-for="skin in battleBus" :key="skin">
          {{ skin.name }}
          <img :src="skin.image" />
          <div>{{ skin.cost }} vbucks</div>
          <button v-on:click="removeSkin(skin)">Remove from battle bus</button>
        </div>
      </div>
    </div>
    <div v-if="page === 'Item Shop'">
      <h1>Item Shop</h1>
      <div class="skins" id="lobby">
        <div v-for="skin in skins" :key="skin">
          {{ skin.name }}
          <img :src="skin.image" />
          <div>{{ skin.cost }} vbucks</div>
          <button v-on:click="addSkin(skin)">Add to battle bus</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
body {
  background-image: 'https://www.internetmatters.org/wp-content/uploads/2019/01/Privacy-settings_Step-01-1024x576.png';
}
h1 {
  text-align: center;
}
.skins {
  display: flex;
  justify-content: space-around;
  flex-flow: column;
}

header {
  justify-content: center;
  text-align: center;
}
</style>
