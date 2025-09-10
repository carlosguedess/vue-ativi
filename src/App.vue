<script setup>
import { ref } from 'vue';
import MeuComponente from './components/MeusComponentes.vue';
// Comentario


const nome = ref('');
const email = ref('');
const telefone = ref('');
const endereco = ref('');
const cpf = ref('');

function cadastrar() {
  // Aqui você pode adicionar a lógica de envio ou validação
  alert(`Cliente cadastrado!\nNome: ${nome.value}\nE-mail: ${email.value}\nTelefone: ${telefone.value}\nEndereço: ${endereco.value}\nCPF: ${cpf.value}`);
  nome.value = '';
  email.value = '';
  telefone.value = '';
  endereco.value = '';
  cpf.value = '';
}
</script>

<template>
  <div class="container">
    <div class="form-card">
      <div class="form-header">
        <h2>Cadastro de Clientes</h2>
        <p>Preencha os dados abaixo para cadastrar um novo cliente.</p>
      </div>
      <form @submit.prevent="cadastrar" class="form-body">
        <div class="form-row">
          <MeuComponente label="Nome completo*" placeholder="Digite o nome completo" v-model="nome" id="nome" required />
        </div>
        <div class="form-row">
          <MeuComponente label="E-mail*" placeholder="Digite o e-mail" v-model="email" id="email" type="email" required />
          <MeuComponente label="Telefone*" placeholder="Digite o telefone" v-model="telefone" id="telefone" type="tel" required />
        </div>
        <div class="form-row">
          <MeuComponente label="Endereço*" placeholder="Digite o endereço" v-model="endereco" id="endereco" required />
          <MeuComponente label="CPF*" placeholder="Digite o CPF" v-model="cpf" id="cpf" required />
        </div>
        <div class="form-actions">
          <Button label="Cadastrar" type="submit" icon="pi pi-user-plus" class="p-button-primary"/>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(120deg, #e0e7ff 0%, #f8fafc 100%);
}

.form-card {
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 6px 32px rgba(30, 41, 59, 0.10);
  padding: 2.5rem 2.5rem 2rem 2.5rem;
  max-width: 480px;
  width: 100%;
  margin: 2rem 1rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-header h2 {
  margin: 0 0 0.3rem 0;
  font-size: 2rem;
  color: #2563eb;
  font-weight: 700;
  letter-spacing: 1px;
}
.form-header p {
  margin: 0;
  color: #64748b;
  font-size: 1.08rem;
}

.form-body {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}

.form-row {
  display: flex;
  gap: 1.2rem;
}

.form-group {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
}

label {
  font-weight: 600;
  color: #222;
  font-size: 1.05rem;
}

input[type="text"],
input[type="email"],
input[type="tel"] {
  padding: 0.7rem 1rem;
  border: 1.5px solid #cbd5e1;
  border-radius: 7px;
  font-size: 1.08rem;
  outline: none;
  transition: border 0.2s;
  width: 100%;
  box-sizing: border-box;
  background: #f1f5f9;
}
input:focus {
  border-color: #46dee4;
  background: #fff;
}

.form-actions {
  margin-top: 1.2rem;
  display: flex;
  justify-content: flex-end;
}
.p-button-primary {
  width: 100%;
  min-width: 160px;
  font-size: 1.15rem;
  padding: 1rem 0;
  border-radius: 7px;
  box-shadow: 0 2px 8px rgba(37,99,235,0.08);
  background: #8e85e5;
  border: none;
}

@media (max-width: 1200px) {
  .form-card {
    max-width: 95vw;
    padding: 2rem 1.2rem 1.2rem 1.2rem;
  }
}
@media (max-width: 900px) {
  .form-card {
    max-width: 99vw;
    padding: 1.2rem 0.5rem 1rem 0.5rem;
    border-radius: 10px;
  }
  .form-header h2 {
    font-size: 1.3rem;
  }
  .form-row {
    flex-direction: column;
    gap: 0.7rem;
  }
  .form-actions {
    justify-content: stretch;
  }
  .p-button-primary {
    width: 100%;
    min-width: unset;
    font-size: 1.05rem;
    padding: 0.8rem 0;
  }
}
@media (max-width: 600px) {
  .form-card {
    padding: 0.7rem 0.2rem;
    border-radius: 8px;
    box-shadow: 0 1px 6px rgba(0,0,0,0.08);
  }
  label {
    font-size: 0.98rem;
  }
  input[type="text"],
  input[type="email"],
  input[type="tel"] {
    font-size: 0.98rem;
    padding: 0.6rem 0.7rem;
  }
  .p-button-primary {
    font-size: 1rem;
    padding: 0.7rem 0;
  }
}
</style>