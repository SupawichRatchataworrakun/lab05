<template>
  <p>Edit the event here</p>

  <!-- สร้างปุ่ม -->
  <button @click="edit">Edit Information!</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    edit() {
      this.$router.push({
        name: 'EventDetails',
        param: { id: this.event.id }
      })

      this.GStore.flashMessage = 'The data has been updated ' 
      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)
    }
  }
}
</script>
