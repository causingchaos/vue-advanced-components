<template>
  <div>
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goals>
      <template #default="slotProps">
        <h2>{{ slotProps.item }}</h2>
        <p>{{ slotProps.anotherProp}}</p>
      </template>
    </course-goals> -->
    <!-- <active-goals v-if="selectedComponent === 'active-goals'"></active-goals>
    <manage-goals v-if="selectedComponent === 'manage-goals'"></manage-goals> -->
    <button v-on:click="setSelectedComponent('active-goals')">Active Goals</button>
    <button v-on:click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <component :is="selectedComponent"></component>
  </div>
</template>

<script>
// import BadgeList from './components/BadgeList.vue';
// import TheHeader from './components/TheHeader.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ManageGoals from './components/ManageGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';

export default {
  components: {
    // 'badge-list': BadgeList,
    // 'the-header': TheHeader,
    ManageGoals,
    ActiveGoals,
    // 'user-info': UserInfo,
    // 'course-goals': CourseGoals,
  },
  data() {
    return {
      selectedComponent: 'active-goals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>