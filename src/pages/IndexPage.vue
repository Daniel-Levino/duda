<template>
  <q-page class="flex flex-center">
    <div class="row">
      <div class="col-12">
        <img
          alt="Quasar logo"
          src="https://m.media-amazon.com/images/I/71b9p7Y3UhL.png"
          style="width: 200px; height: 200px"
        >
      </div>
      <div class="col-12 q-mt-md">
        <q-btn to="/cliente">Cliente</q-btn>
      </div>
      <div class="col-12 q-mt-md">
        <q-btn>Estabelecimento</q-btn>
      </div>
    </div>
  </q-page>
</template>

<script>
import {mapActions} from "vuex";

export default ({
  name: 'IndexPage',
  methods: {
    ...mapActions('cliente', ['ActionClienteLogin']),
    login() {
      this.ActionClienteLogin('ok');
    }
  }
})
</script>
