<template>
  <div>
    <vue-headful title="Registro Ojeadores | FuturasEstrellas"/>
    <h1>REGISTRO DE OJEADORES</h1>
    <p v-show="missingParamsMsg" id="camposVacios">Hay algún campo vacío</p>
    <div id="formularioRegistro" class="mensajeError">
      <div class="input_field">
        <label for="nombre">Nombre del/la ojeador/a:</label>
        <input type="text" name="nombre" v-model="nombre" placeholder="Nombre">
      </div>

      <div class="input_field">
        <label for="apellidos">Apellidos del/la ojeador/a:</label>
        <input type="text" name="apellidos" v-model="apellidos" placeholder="Apellidos">
      </div>

      <div class="input_field">
        <label for="email">Email:</label>
        <input type="text" name="email" v-model="email" placeholder="Email">
      </div>

      <div class="input_field">
        <label for="sexo">Sexo del/la ojeador/a:</label>
        <select v-model="sexo" name="sexo" id="sexo">
          <option value="Hombre">Hombre</option>
          <option value="Mujer">Mujer</option>
        </select>
      </div>

      <div class="input_field">
        <label for="provincia">Seleccione la provincia de residencia:</label>
        <select v-model="provincia" name="provincia" id="provincia">
          <option value='Álava'>Álava</option>
          <option value='Albacete'>Albacete</option>
          <option value='Alicante/Alacant'>Alicante/Alacant</option>
          <option value='Almería'>Almería</option>
          <option value='Asturias'>Asturias</option>
          <option value='Ávila'>Ávila</option>
          <option value='Badajoz'>Badajoz</option>
          <option value='Barcelona'>Barcelona</option>
          <option value='Burgos'>Burgos</option>
          <option value='Cáceres'>Cáceres</option>
          <option value='Cádiz'>Cádiz</option>
          <option value='Cantabria'>Cantabria</option>
          <option value='Castellón/Castelló'>Castellón/Castelló</option>
          <option value='Ceuta'>Ceuta</option>
          <option value='ciudadCiudad Realreal'>Ciudad Real</option>
          <option value='Córdoba'>Córdoba</option>
          <option value='Cuenca'>Cuenca</option>
          <option value='Girona'>Girona</option>
          <option value='Las Palmas'>Las Palmas</option>
          <option value='Granada'>Granada</option>
          <option value='Guadalajara'>Guadalajara</option>
          <option value='Guipúzcoa'>Guipúzcoa</option>
          <option value='Huelva'>Huelva</option>
          <option value='Huesca'>Huesca</option>
          <option value='Illes Balears'>Illes Balears</option>
          <option value='Jaén'>Jaén</option>
          <option value='A Coruña'>A Coruña</option>
          <option value='La Rioja'>La Rioja</option>
          <option value='León'>León</option>
          <option value='Lleida'>Lleida</option>
          <option value='Lugo'>Lugo</option>
          <option value='Madrid'>Madrid</option>
          <option value='Málaga'>Málaga</option>
          <option value='Melilla'>Melilla</option>
          <option value='Murcia'>Murcia</option>
          <option value='Navarra'>Navarra</option>
          <option value='Ourense'>Ourense</option>
          <option value='Palencia'>Palencia</option>
          <option value='Pontevedra'>Pontevedra</option>
          <option value='Salamanca'>Salamanca</option>
          <option value='Segovia'>Segovia</option>
          <option value='Sevilla'>Sevilla</option>
          <option value='Soria'>Soria</option>
          <option value='Tarragona'>Tarragona</option>
          <option value='Santa Cruz de Tenerife'>Santa Cruz de Tenerife</option>
          <option value='Teruel'>Teruel</option>
          <option value='Toledo'>Toledo</option>
          <option value='Valencia/Valéncia'>Valencia/Valéncia</option>
          <option value='Valladolid'>Valladolid</option>
          <option value='Vizcaya'>Vizcaya</option>
          <option value='Zamora'>Zamora</option>
          <option value='Zaragoza'>Zaragoza</option>
        </select>
      </div>
        
      <p v-show="ageErrorMsg" id="edadInvalida" class="mensajeError">Los ojeadores deben ser mayores de edad</p>

      <div class="input_field">
        <label for="fechaNacimiento">Fecha de nacimiento del/la ojeador/a: (debe ser mayor de edad)</label>
        <input type="date" v-model="fechaNacimiento" placeholder="yyyy-mm-dd">
      </div>
      
      <div class="input_field">
        <label for="clubActual">Club actual del/la ojeador/a:</label>
        <input type="text" v-model="clubActual" placeholder="Club actual">
      </div>

      <div class="input_field">
        <label for="categoria">Categoría que busca el/la ojeador/a:</label>
        <select v-model="categoria" name="categoria" id="categoria">
          <option value="Prebenjamín">Prebenjamín</option>
          <option value="Benjamín">Benjamín</option>
          <option value="Alevín">Alevín</option>
          <option value="Infantil">Infantil</option>
          <option value="Cadete">Cadete</option>
          <option value="juveJuvenilnil">Juvenil</option>
        </select>
      </div>
      
      <div class="input_field">
        <label for="posicionPrincipal">Posición principal que busca el/la ojeador/a:</label>
        <select v-model="posicion" name="posicionPrincipal" id="posicionPrincipal">
          <option value="Portero">Portero</option>
          <option value="Lateral Derecho">Lateral Derecho</option>
          <option value="Lateral Izquierdo">Lateral Izquierdo</option>
          <option value="Central Derecho">Central Derecho</option>
          <option value="Central Izquierdo">Central Izquierdo</option>
          <option value="Mediocentro Defensivo">Mediocentro Defensivo</option>
          <option value="Mediocentro Creador">Mediocentro Creador</option>
          <option value="Mediocentro Ofensivo">Mediocentro Ofensivo</option>
          <option value="Extremo Derecho">Extremo Derecho</option>
          <option value="Extremo Izquierdo">Extremo Izquierdo</option>
          <option value="Delantero">Delantero</option>
        </select>
      </div>

      <div class="input_field">
        <label for="piernaBuena">Pierna buena que busca el/la ojeador/a:</label>
        <select v-model="piernaBuena" name="piernaBuena" id="piernaBuena">
          <option value="Derecha">Derecha</option>
          <option value="Izquierda">Izquierda</option>
          <option value="Ambas">Ambas</option>
        </select>
      </div>

      <div class="input_field">
        <label for="avatar">Avatar de perfil:</label>
        <input type="file" name="avatar" id="avatar" accept="image/x-png,image/jpeg" @change="avatarPerfil">
      </div>

      <p v-show="invalidPasswordMsg" id="contrasenaInvalida" class="mensajeError">La contraseña que has introducido no es válida</p>
      <p v-show="passwordsDontMatchMsg" id="contrasenasDiferentes" class="mensajeError">Las contraseñas introducidas no coinciden</p>

      <div class="input_field">
        <label for="contrasena">Introduzca una contraseña:</label>
        <input type="password" name="password" v-model="contrasena" placeholder="contraseña">
      </div>

      <div class="input_field">
        <label for="confirmarContrasena">Confirmar contraseña:</label>
        <input type="password" name="confirmPassword" v-model="confirmarContrasena" placeholder="contraseña">
      </div>
    </div>
    <button @click="validatingData()">Registrarse</button>
  </div>
</template>

<script>
import Swal from 'sweetalert2';
import axios from 'axios';
import moment from 'moment'

export default {
  name: "RegistroFamilia",
  data() {
    return {
      nombre: '',
      apellidos: '',
      email: '',
      sexo: '',
      provincia: '',
      fechaNacimiento: '',
      clubActual: '',
      categoria: '',
      posicion: '',
      piernaBuena: '',
      contrasena: '',
      confirmarContrasena: '',
      selectedFile: null,
      missingParamsMsg: false,
      invalidPasswordMsg: false,
      passwordsDontMatchMsg: false,
      ageErrorMsg: false

    }
  },
  methods: {
    validatingData() {
      if(this.nombre === '' || this.apellidos === '' || this.email === '' || this.sexo === '' || this.provincia === '' || this.fechaNacimiento === '' || this.clubActual === '' || this.categoria === '' || this.posicion === '' || this.piernaBuena === '' || this.contrasena === '' || this.confirmarContrasena === '') {
        this.missingParamsMsg = true;
        Swal.fire({
            title: 'No puede haber campos vacíos!',
            text: 'Debes rellenar todos los campos para poder añadir un nuevo cliente',
            icon: 'error',
            confirmButtonText: 'OK',
        })
      } else if(moment().diff(this.fechaNacimiento, 'years') < 18) {
          this.ageErrorMsg = true;
          Swal.fire({
            title: 'El ojeador debe ser mayor de edad!',
            text: 'Debes ser mayor de edad para registrarte como ojeador',
            icon: 'error',
            confirmButtonText: 'OK',
        })
      } else if(this.contrasena.length < 8 || this.contrasena.toLowerCase() === this.contrasena || /\d/.test(this.contrasena) === false) {
          this.invalidPasswordMsg = true;
          Swal.fire({
            title: 'Tu contraseña no es válida!',
            text: 'La contraseña debe tener al menos 8 caracteres, una mayúscula y un número',
            icon: 'error',
            confirmButtonText: 'OK',
        })
      } else if (this.contrasena !== this.confirmarContrasena){
        this.passwordsDontMatchMsg = true
        Swal.fire({
            title: 'Tus contraseñas no coinciden!',
            text: 'Las contraseñas deben ser iguales',
            icon: 'error',
            confirmButtonText: 'OK',
        })
      } else {
        this.registrarOjeador();
        this.missingParamsMsg = false;
        this.invalidPasswordMsg = false;
        this.passwordsDontMatchMsg = false;
        this.ageErrorMsg = false;
      }
    },
    avatarPerfil(event) {
      this.selectedFile = event.target.files[0]
    },
    registrarOjeador () {
      let self = this;
      let fd = new FormData();
      fd.set('name', self.nombre)
      fd.set('surname', self.apellidos)
      fd.set('email', self.email)
      fd.set('gender', self.sexo)
      fd.set('province', self.provincia)
      fd.set('birthDate', self.fechaNacimiento)
      fd.set('actualClub', self.clubActual)
      fd.set('category', self.categoria)
      fd.set('position', self.posicion)
      fd.set('strongLeg', self.piernaBuena)
      fd.set('password', self.contrasena)
      fd.set('confirmPassword', self.confirmarContrasena)
      fd.append('avatarPerfil', self.selectedFile)
      axios.post('http://localhost:7000/registroOjeador',
      fd,
      {
        headers: {
          'Content-Type': 'multipart/form-data'
        }
      })
      .then(res => {
        console.log(res)
      })
      .catch(err => {
        console.log(err)
      })
      self.nombre = '';
      self.apellidos = '',
      self.email = '',
      self.sexo = '',
      self.provincia = '',
      self.fechaNacimiento = '',
      self.clubActual = '',
      self.categoria = '',
      self.posicion = '',
      self.piernaBuena = '',
      self.contrasena = '',
      self.confirmarContrasena = '',
      self.selectedFile = null
      this.$router.push('/loginojeador')
    }
  }
};
</script>

<style scoped>
#formularioRegistro {
  background-color: #fff;
  max-width: 700px;
  width: 80%;
  margin: 20px auto;
  padding: 1rem;
  border-radius: 1rem;
  box-shadow: 0px 0px 10px #78a5d68f;
}
input {
  padding: .5rem;
  border: 1px solid #f08848;
  background-color: #fff;
  width: 100%;
  border-radius: .2rem;
  transition: all .3s ease-in-out
}
input:focus {
  background-color: #abd2fb8f;
}
input:hover {
  background-color: #abd2fb8f;
}
select {
  padding: .5rem;
  border: 1px solid #f08848;
  border-radius: .2rem;
  width: 100%;
  transition: all .3s ease-in-out;
  background-color: #fff;
}
select:focus {
  background-color: #beddff8f;
}
select:hover {
  background-color: #abd2fb8f;
}
.input_field {
  display:flex;
  align-items: center;
  margin-bottom: 1rem;
}
 .input_field label {
  width: 600px;
  padding-left: 1rem;
  text-align: left;
}
button {
  color: #35495E;
  font-weight: 700;
  padding: .5rem;
  text-transform: uppercase;
  text-decoration: none;
  background: #f08848a1;
  border-radius: .5rem;
  display: inline-block;
  border: none;
  transition: all 0.4s ease 0s
}
button:hover  {
  text-shadow: 0px 0px 6px #8dc4ff;
  box-shadow: 4px 4px 1px 1px #4e79a7;
  transition: all 0.4s ease 0s;
  cursor: pointer;
  background-color: #8dc4ff;
}
@media screen and (max-width: 480px) {
  .input_field {
    flex-direction: column;
    align-items: flex-start
}
#formularioRegistro {
  margin: 1rem;
  padding-top: 2rem;
  font-size: 90%;
}
select {
  padding: .3rem;
  width: 95%;
}
input {
  padding: .3rem;
  width: 95%;
  transition: all .3s ease-in-out
}
.input_field label {
  width: auto;
  padding-left: 1rem;
  text-align: left;
}
}
</style>