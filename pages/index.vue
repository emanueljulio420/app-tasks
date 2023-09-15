<template>
  <div class="d-flex align-center flex-column my-16">
    <v-card>
      <v-card-title class="text-center">
        <h1 class="my-5"> Inicio de sesion </h1>
      </v-card-title>
      <v-card-text>
        <v-sheet width="700" class="mx-auto my-auto">
          <v-form action="javascript:void(0)" ref="form" @submit="entrar">
            <v-text-field label="Email" v-model="user.email" density="compact" placeholder="Email address"
              variant="outlined"></v-text-field>
            <v-text-field label="Password" v-model="user.contra" :type="'password'" density="compact" placeholder="Enter your password"
              variant="outlined">
            </v-text-field>
            <v-btn type="submit" block color="deep-purple-darken-1">Ingresar</v-btn>
          </v-form>
        </v-sheet>
      </v-card-text>
    </v-card>
  </div>
</template>
<script setup>
definePageMeta({
  layout: "blank",
});

const user = ref({ })

const router = useRouter()

const entrar = () =>{
  if (user.value.email === 'nada@gmail.com' && user.value.contra === 'monda123'){
    router.push({
      path: "/tareas"
    })
  }
  else{
    alert('Usuario incorrecto')
  }
}

</script>
