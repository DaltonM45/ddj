<template>
  <div>
    <!-- <ul class="menu">
            <li><router-link to="/">Inicio</router-link></li>
            <li><router-link to="/contactos">Contactos</router-link></li>
            <li><router-link to="/about">Acerca de</router-link></li>
             <li> <p @click="$router.push('/sesion')">iniciar sesion</p></li> 
    </ul>-->
    <div class="menu">
      <div class="sub-menu">
        <div class="head-min">
          <div class="guvu-tit">
            <p id="guvu">Guvu</p>
          </div>

          <div class="toggle-menu">
            <i class="fas fa-bars barra" v-on:click="abrirMenu()"></i>
          </div>
        </div>
        <div class="opciones" v-show="permiso">
          <div class="op">
            <router-link :to="{name: '/'}">
              <p>inicio</p>
            </router-link>
          </div>
          <div class="op">
            <router-link :to="{name: 'contactos'}">
              <p>Contactos</p>
            </router-link>
          </div>
          <div class="op">
            <router-link :to="{name: 'about'}">
              <p>Acerca de</p>
            </router-link>
          </div>
          <div class="op">
            <p>Acerca de</p>
          </div>
          <div class="op">
            <p>iniciar sesion</p>
          </div>
          <div class="op">
            <p>Registrate</p>
          </div>
        </div>
        <div class="opciones2" v-show="!permiso">
          <div class="op">
            <router-link :to="{name: '/'}">
              <p>inicio</p>
            </router-link>
          </div>
          <div class="op">
            <router-link :to="{name: 'contactos'}">
              <p>Contactos</p>
            </router-link>
          </div>
          <div class="op">
            <router-link :to="{name: 'about'}">
              <p>Acerca de</p>
            </router-link>
          </div>
          <div class="op">
            <p>Acerca de</p>
          </div>
          <div class="op">
            <p>iniciar sesion</p>
          </div>
          <div class="op">
            <p>Registrate</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      permiso: false
    };
  },
  methods: {
    abrirMenu() {
      this.permiso = !this.permiso;
      console.log(this.permiso);
    }
  }
};
</script>

<style scoped>
@font-face {
  font-family: "roboto";
  src: url("/fonts/Roboto-Regular.ttf");
}
@font-face {
  font-family: "AsapSemibold";
  src: url("/fonts/Asap-SemiBold.ttf");
}

.menu {
  font-family: "roboto";
  /* background-color: rgb(15, 17, 15); */
  box-shadow: 0px 1px 5px 0px rgba(0, 0, 0, 0.1);
  padding: 15px;
  border-radius: 6px;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 1030;
}
#guvu {
  color: #000;
  cursor: pointer;
}

#botoncheck {
  display: none;
}

.sub-menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.showmenu {
  background: #fa0000;
  display: block;
  flex-direction: column;
}

.sub-menu .toggle-menu {
  display: none;
}

.sub-menu .head-min .toggle-menu .barra {
  font-size: 22px;
}
.sub-menu .guvu-tit p {
  font-family: "AsapSemibold";
  margin-bottom: 0px;
  font-size: 24px;
  margin-left: 12px;
  color: #000;
}

.sub-menu .opciones {
  display: flex;
  font-size: 14px;
}
.sub-menu .opciones .op {
  margin-right: 10px;
  margin-left: 10px;
  padding: 10px 20px;
  display: flex;
  cursor: pointer;
}
.sub-menu .opciones .op:hover {
  background: #069370;
  color: #fff;
  transition: 0.5s;
}
.sub-menu .opciones p {
  margin-bottom: 0px;
}

/* OPCIONES 2 */
.sub-menu .opciones2 {
  display: flex;
  font-size: 14px;
}
.sub-menu .opciones2 .op {
  margin-right: 10px;
  margin-left: 10px;
  padding: 10px 20px;
  display: flex;
  cursor: pointer;
}
.sub-menu .opciones2 .op:hover {
  background: #069370;
  color: #fff;
  transition: 0.5s;
}
.sub-menu .opciones2 p {
  margin-bottom: 0px;
}

/* RESPONSIVE */

@media (max-width: 870px) {
  .sub-menu {
    display: block;
  }
  .sub-menu .head-min {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .sub-menu .head-min .toggle-menu {
    display: block;
    cursor: pointer;
  }
  .sub-menu .opciones {
    flex-direction: column;
  }
  .sub-menu .opciones .op {
    text-align: center;
  }

  .sub-menu .opciones2 {
    display: none;
  }
}
</style>
