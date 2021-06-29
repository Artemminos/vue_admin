<template>
  <div class="sidebar">
    <div class="sidebar__logo">
      <div class="sidebar__logo-title">
        <img alt="" src="../../assets/logo.svg">
        <span>Vuesax</span>
      </div>
      <img alt="" src="../../assets/Oval.svg">
    </div>
    <div class="sidebar__content">
      <Select :items="arr" :name="'Dashboard'">
        <template v-for="item in arr" :key="item">
          <router-link :active-class="'sidebar__content__link__active'" class="sidebar__content__link white_oval_icon"
                       :to='{path:item.path}'>
            {{item.name}}
          </router-link>
        </template>
      </Select>
      <div class="sidebar__content__group">
        <span class="sidebar__content__group__title">
          APPS
        </span>
        <router-link class="sidebar__content__link email_icon arrow_icon" to="/about">Email</router-link>
      </div>
    </div>

  </div>
</template>

<script>
import Select from "./Select.vue";

export default {
  name: "Sidebar",
  data() {
    return{
      arr:[
        {
          path:'/',
          name:'Главная'
        },
        {
          path:'/about',
          name:'Не главная'
        }
      ]
    }
  },
  components: {
    Select
  },
  methods: {
    log(item){
      console.log(item);
    }
  }


};
</script>

<style scoped>

</style>
