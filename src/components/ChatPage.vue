<template>
  <f7-page>
    <f7-navbar title="Chat" />
    <f7-messagebar
        ref="messagebar"
        v-model:value="messageText"
        :placeholder="placeholder"
        :attachments-visible="attachmentsVisible"
        :sheet-visible="sheetVisible"
    >
      <template #inner-end>
        <f7-link
            icon-ios="f7:arrow_up_circle_fill"
            icon-aurora="f7:arrow_up_circle_fill"
            icon-md="material:send"
            @click="sendMessage"
        />
      </template>
    </f7-messagebar>
    <f7-messages>
      <f7-message
          v-for="(message, index) in messagesData"
          :key="index"
          :type="message.type"
          :name="message.name"
      >
        <template #text>
          <!-- eslint-disable-next-line -->
          <span v-if="message.text" v-html="message.text"></span>
        </template>
      </f7-message>
<!--      <f7-message-->
<!--          v-if="typingMessage"-->
<!--          type="received"-->
<!--          :typing="true"-->
<!--          :first="true"-->
<!--          :last="true"-->
<!--          :tail="true"-->
<!--          :header="`${typingMessage.name} is typing`"-->
<!--          :avatar="typingMessage.avatar"-->
<!--      ></f7-message>-->
    </f7-messages>
  </f7-page>
</template>

<script>
import { f7, f7ready } from 'framework7-vue';
import $ from 'dom7';

export default {
  name: 'ChatPage',
  components: {},
  filters: {},
  props: {},
  data () {
    return {
      messageText: '',
      placeholder: 'Message',
      attachmentsVisible: false,
      sheetVisible: false,
      messagesData: [
        {
          type: 'sent',
          text: 'Hi, Kate',
        },
        {
          type: 'sent',
          text: 'How are you?',
        },
        {
          name: 'Kate',
          type: 'received',
          text: 'Hi, I am good!',
        }
      ],
    }
  },
  computed: {},
  watch: {},
  beforeCreate () {},
  created () {},
  beforeMount () {},
  mounted () {},
  beforeUpdate () {},
  updated () {},
  activated () {},
  deactivated () {},
  beforeDestroy () {},
  destroyed () {},
  methods: {
    sendMessage() {
      this.messagesData.push({
        text: this.messageText,
        type: 'sent',
        name: 'me'
      })
      this.messageText = ''
    }
  }
}
</script>

<style scoped lang='scss'>

</style>
