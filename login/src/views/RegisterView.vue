<template>
  <v-container>
    <v-row align="center" justify="center">
      <v-col cols="12" sm="10">
        <v-card class="elevation-6 mt-10">
          <v-window v-model="step">
            <!-- Page de connexion -->
            <v-window-item :value="1">
              <v-row>
                <v-col cols="12" md="6">
                  <v-card-text class="mt-12">
                    <h1 class="text-center  mb-5 " style="color:hsl(268, 70%, 30%)">Bienvenue de nouveau !</h1>
                    <h5 class="text-center grey--text">
                      Connectez-vous à votre compte pour continuer à gérer<br />
                      vos tâches efficacement.
                    </h5>
                    <v-row align="center" justify="center">
                      <v-col cols="12" sm="8">
                        <v-text-field
                          label="Email"
                          outlined
                          dense
                          color="hsl(268, 70%, 30%)"
                          class="mt-16"
                        />
                        <v-text-field
                          label="Mot de passe"
                          outlined
                          dense
                          color="hsl(268, 70%, 30%)"
                          type="password"
                        />
                        <v-row>
                          <v-col cols="12" sm="7">
                            <v-checkbox
                              label="Se souvenir de moi"
                              class="mt-n1"
                              color="hsl(268, 70%, 30%)"
                            ></v-checkbox>
                          </v-col>
                          <v-col cols="12" sm="5">
                            <span class="caption purple--text"
                              >Mot de passe oublié</span
                            >
                          </v-col>
                        </v-row>
                        <v-btn color="hsl(268, 70%, 30%)" dark block tile @click="login">Se connecter</v-btn>
                        <h5 class="text-center grey--text mt-4 mb-3">
                          Ou connectez-vous avec
                        </h5>
                        <div
                          class="d-flex justify-space-between align-center mx-10 mb-16"
                        >
                          <v-btn depressed outlined color="grey">
                            <v-icon color="red">fab fa-google</v-icon>
                          </v-btn>
                          <v-btn depressed outlined color="grey">
                            <v-icon color="blue">fab fa-facebook-f</v-icon>
                          </v-btn>
                          <v-btn depressed outlined color="grey">
                            <v-icon color="black">fab fa-apple</v-icon>
                          </v-btn>
                        </div>
                      </v-col>
                    </v-row>
                  </v-card-text>
                </v-col>
                <v-col cols="12" md="6" class="purple_bg rounded-bl-xl">
                  <div style="text-align: center; padding: 180px 0;">
                    <v-card-text class="white--text">
                      <h3 class="text-center">Pas encore inscrit(e) ?</h3>
                      <h6 class="text-center">
                        Créez un compte pour commencer à organiser vos tâches et
                        atteindre vos objectifs.
                      </h6>
                    </v-card-text>
                    <div class="text-center">
                      <v-btn tile outlined dark @click="step++">S'inscrire</v-btn>
                    </div>
                  </div>
                </v-col>
              </v-row>
            </v-window-item>

            <!-- Page d'inscription -->
            <v-window-item :value="2">
              <v-row><v-col cols="12" md="6" class="purple_bg rounded-br-xl">
                  <div style="text-align: center; padding: 180px 0;">
                    <v-card-text class="white--text">
                      <h3 class="text-center">Déjà inscrit(e) ?</h3>
                      <h6 class="text-center">
                        Connectez-vous à votre compte pour continuer à gérer vos
                        tâches.
                      </h6>
                    </v-card-text>
                    <div class="text-center">
                      <v-btn tile outlined dark @click="step--">
                        Se connecter
                      </v-btn>
                    </div>
                  </div>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card-text class="mt-12">
                    <h1 class="text-center mb-4" style="color:hsl(268, 70%, 30%)">Créer un compte</h1>
                    <h5 class="text-center grey--text">
                      Inscrivez-vous pour organiser votre emploi du temps et vos
                      objectifs.
                    </h5>
                    <v-row align="center" justify="center">
                      <v-col cols="12" sm="8">
                        <v-row>
                          <v-col cols="12" sm="6">
                            <v-text-field
                              label="Prénom"
                              outlined
                              dense
                               color= "hsl(268, 70%, 30%)"
                              class="mt-4"
                              v-model="name"
                            />
                          </v-col>
                          <v-col cols="12" sm="6">
                            <v-text-field
                              label="Nom"
                              outlined
                              dense
                               color= "hsl(268, 70%, 30%)"
                              class="mt-4"
                              v-model="surname"
                            />
                          </v-col>
                        </v-row>
                        <v-text-field
                          label="Email"
                          outlined
                          dense
                          color= "hsl(268, 70%, 30%)"
                          v-model="email"
                        />
                        <v-text-field
                          label="Mot de passe"
                          outlined
                          dense
                          color= "hsl(268, 70%, 30%)"
                          type="password"
                          v-model="password"
                        />
                        <v-row>
                          <v-col cols="12" sm="7">
                            <v-checkbox
                              label="J'accepte les termes et conditions"
                              class="mt-n1 ma-auto" style="max-width: 400px;"
                              color= "hsl(268, 70%, 30%)"
                            ></v-checkbox>
                          </v-col>
                        </v-row>
                        <v-btn   color= "hsl(268, 70%, 30%)" dark block tile @click="signup">S'inscrire</v-btn>
                        <h5 class="text-center grey--text mt-4 mb-3">
                          Ou inscrivez-vous avec
                        </h5>
                        <div
                          class="d-flex justify-space-between align-center mx-10 mb-11"
                        >
                          <v-btn depressed outlined color="grey">
                            <v-icon color="red">fab fa-google</v-icon>
                          </v-btn>
                          <v-btn depressed outlined color="grey">
                            <v-icon color="blue">fab fa-facebook-f</v-icon>
                          </v-btn>
                          <v-btn depressed outlined color="grey">
                            <v-icon color="black">fab fa-apple</v-icon>
                          </v-btn>
                        </div>
                      </v-col>
                    </v-row>
                  </v-card-text>
                </v-col>
              </v-row>
            </v-window-item>
          </v-window>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>

import axios from "axios";

export default {
  data: () => ({
  step: 1,
  name: "",
  surname: "",
  email: "",
  password: "",

  }),
  methods: {

    async login() {
      try {
        const response = await axios.post("http://localhost:3000/login", {
          email: this.email,
          password: this.password,
        });
        alert(response.data.message); // Affiche le message de bienvenue
      } catch (error) {
        alert(error.response?.data?.message || "Une erreur est survenue");
      }
    },
    async signup() {
  try {
    const response = await axios.post("http://localhost:3000/signup", {
      name: this.name,
      surname: this.surname,
      email: this.email,
      password: this.password,
    });
    alert(response.data.message); // Affiche le message de succès
    this.step = 1; // Retourne à la page de connexion
  } catch (error) {
    alert(error.response?.data?.message || "Une erreur est survenue");
  }
},











  },


};






</script>

<style scoped>
.v-application .rounded-bl-xl {
  border-bottom-left-radius: 300px !important;
}
.v-application .rounded-br-xl {
  border-bottom-right-radius: 300px !important;
}
.purple_bg {
  background-color: hsl(268, 70%, 30%);
}
</style>