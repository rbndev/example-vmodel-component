<template>
  <div class="card">
    <TextEntrada
      label="Login"
      :required="true"
      type="text"
      placeholder="Digite seu Login"
      v-model:vmodel="login"
    />
    <TextEntrada
      label="Senha"
      :required="false"
      type="password"
      placeholder="******"
      v-model:vmodel="senha"
    />
    <!-- TODO:fix teste -->
    <div class="center">
      <Button label="Cancelar" color="secondary" />
      <Button label="Logar" color="primary" @click="logar" />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import TextEntrada from "./components/TextEntrada.vue";
import Button from "./components/Button.vue";

export default {
  components: {
    TextEntrada,
    Button,
  },
  setup() {
    const login = ref();
    const senha = ref();
    // TODO: logica logar
    const logar = () => {
      console.log(`Login: ${login.value} Senha: ${senha.value}`);
    };

    return { login, senha, logar };
  },
};
</script>

<style scoped>
.card {
  width: 300px;
  background: #ededed;
  padding: 20px;
  border-radius: 16px;
  box-shadow: 0 0 6px 0px #ededed;
}
.center {
  display: flex;
  justify-content: center;
  gap: 8px;
}
</style>