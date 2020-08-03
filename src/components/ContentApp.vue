<template>
  <div>
    <v-app id="inspire">
      <v-main>
        <div class="margenes grey lighten-5">
          <v-row no-gutters>
            <v-col class="pa-2" cols="6" md="4">
              <v-card class=""  id="drag-items">
                <v-toolbar flat color="cyan darken-3" dark>
                  <v-toolbar-title>TrukiEmociones</v-toolbar-title>
                  <v-spacer></v-spacer>

                <v-btn id="download" v-on:click="tomarFoto"  icon >                  
                  <v-icon  dark>mdi-camera</v-icon>
                </v-btn>
                
                </v-toolbar>
                <v-tabs  vertical>
                  <v-tab>
                    ¿Como eres?
                  </v-tab>
                  <v-tab>
                    Emociones
                  </v-tab>
                  <v-tab>
                    Sensaciones
                  </v-tab>

                  <v-tab-item>
                    <v-card flat>
                      
                      <img class="imagen" src="@/assets/img/TrukiEmociones/cara1.png" draggable="true">
                      <img class="imagen" src="@/assets/img/TrukiEmociones/cara2.png" draggable="true">
                    </v-card>
                  </v-tab-item>
                  <v-tab-item>
                    <v-card flat>
                     <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-07.png" draggable="true">
                     <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-08.png" draggable="true">
                     <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-09.png" draggable="true">
                     <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-10.png" draggable="true">
                     <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-11.png" draggable="true">
                     <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-12.png" draggable="true">
                    </v-card>
                  </v-tab-item>
                  <v-tab-item>
                    <v-card flat>
                      <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-01.png" draggable="true">
                      <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-02.png" draggable="true">
                      <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-03.png" draggable="true">
                      <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-04.png" draggable="true">
                      <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-05.png" draggable="true">
                      <img class="imagen" src="@/assets/img/TrukiEmociones/elementos_juego-06.png" draggable="true">
                    </v-card>
                  </v-tab-item>
                </v-tabs>
              </v-card>
            </v-col>
            <v-col class="pa-2" cols="12" sm="6" md="8">
              <v-card class="pa-2" outlined tile>
                <div id="container"></div>
              </v-card>
            </v-col>
          </v-row>
        </div>
      </v-main>
    </v-app>
  </div>
</template>

<script>
import Vue from 'vue';
import html2canvas from 'html2canvas';
 
Vue.use(html2canvas);


export default {
  methods: {
    tomarFoto(){
      console.log("Funciono")
       document.getElementById("download").addEventListener("click", function() {

        html2canvas(document.querySelector('#container')).then(function(canvas) {
        
            console.log(canvas);
            saveAs(canvas.toDataURL(), 'Foto-Sesion.png');
        });
        });
        
        
        function saveAs(uri, filename) {
        
        var link = document.createElement('a');
        
        if (typeof link.download === 'string') {
        
            link.href = uri;
            link.download = filename;
        
            //Firefox requires the link to be in the body
            document.body.appendChild(link);
        
            //simulate click
            link.click();
        
            //remove the link when done
            document.body.removeChild(link);
        
        } else {
        
            window.open(uri);
        
        }
        }
    }
  }
};
</script>

<style>
.margenes {
  margin: 20px;
}

.separador{
}

.imagen{
  max-width: 160px;
  margin: 5px;
}
</style>