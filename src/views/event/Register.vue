<template>
  <p>Regstration form here</p>
  <!-- สร้างปุ่ม -->
  <button @click="register">Register Me!</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'], // <-- Inject the Global Store
  // register function
  methods: {
    register() {
      //Assuming successful API call to register them

      //Set a flash message to appear on the next page loaded which says
      // 'You are successfully registered for ' + this.event.title

      this.$router.push({
        name: 'EventDetails',
        param: { id: this.event.id}
      }) 
      
      //ขึ้้นโชว์ข้อความ
      this.GStore.flashMessage =
        'You are successfully registered for ' + this.event.title
      setTimeout(() => {
        //After 3 remove it
        this.GStore.flashMessage = ''
      }, 3000)

      //Set a flash message to appear on the next page loaded which says
    }
  }
}
</script>
