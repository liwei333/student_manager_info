<template>
  <div
    class="toast"
    v-if="flag"
    :class="{'fade-in':show,'fade-out':!show,success:status == 'success',fail:status=='fail'} "
  >
    <div v-if="status === 'success'" style="color:#4bad15">√{{msg}}</div>
    <div v-if="status === 'fail'" style="color:#ec1b1b">×{{msg}}</div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.success {
  background: #a5fa73;
}
.fail {
  background: #f99;
}
.toast {
  position: fixed;
  top: 40px;
  left: 50%;
  transform: translateX(-50%);
  padding: 15px;

  border-radius: 3px;
}

.fade-in {
  animation: fadein 0.3s;
}

.fade-out {
  animation: fadeout 0.3s;
}

@keyframes fadein {
  0% {
    top: 0;
    opacity: 0;
  }

  100% {
    top: 40px;
    opacity: 1;
  }
}

@keyframes fadeout {
  100% {
    top: 0;
    opacity: 0;
  }

  0% {
    top: 40px;
    opacity: 1;
  }
}
</style>