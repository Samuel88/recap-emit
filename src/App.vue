<script>
import NotifySender from './components/NotifySender.vue';
import NotifyViewer from './components/NotifyViewer.vue';

export default {
  components: {
    NotifySender,
    NotifyViewer,
  },
  data() {
    return {
      notifies: [],
    };
  },
  methods: {
    onNotifySend({ testo }) {
      this.notifies.push(testo);
    },
    onNotifyRemove(index) {
      this.notifies.splice(index, 1);
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>Notification Sender</h1>
    <NotifyViewer @notify-remove="onNotifyRemove" :notifies="notifies" />
    <NotifySender @notify-send="onNotifySend" />
  </div>
</template>