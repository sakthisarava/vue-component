<template>
  <div>
    <the-header></the-header>
    <!-- <TheHeader /> -->
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <!-- <active-goals v-if="selecteComponent === 'active-goals'"></active-goals>
    <manage-goals v-if="selecteComponent === 'manage-goals'"></manage-goals> -->
    <keep-alive>
    <component :is="selecteComponent"></component>
    </keep-alive> 
  </div>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue'

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals
  },
  data() {
    return {
      selecteComponent: 'active-goals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selecteComponent = cmp;
    }
  }
};
</script>

<style scope>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>