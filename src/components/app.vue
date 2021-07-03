<template>
  <f7-app v-bind="f7params">
    <f7-view main url="/"></f7-view>
  </f7-app>
</template>

<script>
import LoginPage from './LoginPage'
import ChatPage from './ChatPage'
export default {
  data() {
    return {
      f7params: {
        name: 'f7-chat',
        routes: [
          {
            path: '/',
            component: LoginPage,
          },
          {
            path: '/chat/',
            component: ChatPage,
          },
        ],
      }
    };
  },
}
</script>
