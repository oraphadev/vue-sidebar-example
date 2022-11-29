<template>
  <aside class="sidebar">
    <header>
      <span>menu</span>
      <h1>Sidebar</h1>
    </header>
    <ul class="menu">
      <li
        v-for="item in items"
        :key="item.title"
        :class="{
          active: active === item.title,
          expanded: item.items && item.items.includes(active),
        }"
        @click.stop="setActive(item.title)"
      >
        <div>
          <span>{{ item.icon }}</span>
          {{ item.title }}
          <span v-if="item.items">expand_more</span>
        </div>
        <ul v-if="item.items" class="submenu">
          <li
            v-for="subitem in item.items"
            :key="subitem"
            :class="{ active: active === subitem }"
            @click.stop="setActive(subitem)"
          >
            <div>
              {{ subitem }}
            </div>
          </li>
        </ul>
      </li>
    </ul>
  </aside>
</template>

<script>
export default {
  name: 'TheSidebar',
  data: () => ({
    active: null,
    items: [
      { title: 'Pessoal', icon: 'person' },
      { title: 'Finanças', icon: 'savings' },
      {
        title: 'Veículos',
        icon: 'directions_car',
        items: [
          'Carros',
          'Motos',
          'Ônibus',
          'Caminhões',
        ],
      },
      {
        title: 'Imóveis',
        icon: 'home',
        items: [
          'Casas',
          'Apartamentos',
          'Chácaras',
          'Bangalôs',
        ],
      },
      { title: 'Viagens', icon: 'beach_access' },
      { title: 'Tarefas', icon: 'task' },
    ],
  }),
  methods: {
    setActive(item) {
      this.active = item
    },
  },
}
</script>

<style scoped>
.sidebar {
  width: 280px;
  height: 100%;
  background: #131215;
}

header {
  height: 80px;
  background: #0e0d0f;
  display: flex;
  align-items: center;
  padding: 0 16px;
  gap: 16px;
}

header span {
  color: #dcdce7;
}

header h1 {
  margin: 0;
  font-size: 24px;
  color: red;
  background: -webkit-linear-gradient(
    45deg,
    #405de6,
    #5851db,
    #833ab4,
    #c13584,
    #e1306c,
    #fd1d1d
  );
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.submenu {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s;
}

li > div {
  display: flex;
  align-items: center;
  height: 50px;
  padding: 0 16px;
  gap: 16px;
  color: #dcdce7;
  cursor: pointer;
}

li.active > div {
  background: linear-gradient(
    45deg,
    #405de6,
    #5851db,
    #833ab4,
    #c13584,
    #e1306c,
    #fd1d1d
  );
}

li.active .submenu,
li.expanded .submenu {
  max-height: 200px;
}

li.active > div > span:nth-child(2),
li.expanded > div > span:nth-child(2) {
  transform: rotate(180deg);
}

li > div > span:nth-child(2) {
  margin-left: auto;
  transition: transform 0.3s;
}
</style>
