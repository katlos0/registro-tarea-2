<template>
    <div class="container">
      <div class="card shadow-lg">
        <div class="card-header text-center bg-primary text-white">Registro de Usuario</div>
        <div class="card-body">
          <form @submit.prevent="register">
            <div class="mb-4">
              <label for="name" class="form-label">Nombre</label>
              <input type="text" v-model="name" id="name" class="form-control" :class="{ 'is-invalid': errorName }" />
              <div class="invalid-feedback" v-if="errorName">El nombre es requerido.</div>
            </div>
  
            <div class="mb-4">
              <label for="lastName" class="form-label">Apellido</label>
              <input type="text" v-model="lastName" id="lastName" class="form-control" :class="{ 'is-invalid': errorLastName }" />
              <div class="invalid-feedback" v-if="errorLastName">El apellido es requerido.</div>
            </div>
  
            <div class="mb-4">
              <label for="email" class="form-label">Email</label>
              <input type="email" v-model="email" id="email" class="form-control" :class="{ 'is-invalid': errorEmail }" />
              <div class="invalid-feedback" v-if="errorEmail">El email es requerido.</div>
            </div>
  
            <div class="mb-4">
              <label for="year" class="form-label">Año</label>
              <input type="text" v-model="year" id="year" class="form-control" :class="{ 'is-invalid': errorYear }" />
              <div class="invalid-feedback" v-if="errorYear">El año es requerido.</div>
            </div>
  
            <div class="mb-4">
              <label for="phone" class="form-label">Teléfono</label>
              <input-phone v-model="phone" id="phone" class="form-control" :class="{ 'is-invalid': errorPhone }" />
              <div class="isnvalid-feedback" v-if="errorPhone">El teléfono es requerido.</div>
            </div>
  
            <div class="mb-4">
              <label for="address" class="form-label">Dirección</label>
              <input type="text" v-model="address" id="address" class="form-control" :class="{ 'is-invalid': errorAddress }" />
              <div class="invalid-feedback" v-if="errorAddress">La dirección es requerida.</div>
            </div>
  
            <button type="submit" class="btn btn-primary w-100">Registrar</button>
          </form>
        </div>
      </div>
  
      <div class="card mt-5 shadow-lg">
        <div class="card-header text-center bg-success text-white">Usuarios Registrados</div>
        <ul class="list-group list-group-flush">
          <li v-for="user in users" :key="user.email" class="list-group-item">
            {{ user.name }} {{ user.lastName }} - {{ user.email }}
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <style scoped>
  .container {
    max-width: 700px;
    padding: 40px;
  }
  
  .card {
    border-radius: 12px;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
  }
  
  .card-header {
    font-size: 1.5rem;
    border-bottom: none;
  }
  
  .form-control {
    border-radius: 0.375rem;
    transition: border-color 0.3s ease-in-out;
  }
  
  .form-control:focus {
    box-shadow: 0 0 5px rgba(0, 123, 255, 0.25);
  }
  
  .btn {
    background-color: #0069d9;
    border-radius: 0.5rem;
    transition: background-color 0.3s ease;
  }
  
  .btn:hover {
    background-color: #0056b3;
  }
  
  .list-group-item {
    font-size: 1rem;
    background-color: #f8f9fa;
  }
  
  .list-group-item:hover {
    background-color: #e9ecef;
  }
  
  h2 {
    font-weight: 500;
    margin-top: 30px;
  }
  </style>
  