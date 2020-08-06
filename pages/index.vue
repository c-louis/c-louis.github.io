<template>
  <div>
    <div class="lc-nav p-4">
      <b-navbar toggleable="sm" type="dark" variant="dark" fixed="top">
        <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>
        <b-navbar-brand>Louis Christ</b-navbar-brand>
        <b-collapse id="nav-text-collapse" is-nav>
          <b-navbar-nav class="mx-auto ml-1">
            <b-nav-item href="#who-am-i">Qui suis-je ?</b-nav-item>
            <b-nav-item href="#studies">Mon Parcours</b-nav-item>
            <b-nav-item href="#my-creations">Mes créations</b-nav-item>
            <b-nav-item href="#contact-me">Me contacter</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <div class="container">
      <div id="who-am-i" class="p-3">
        <h1 class="mx-auto">Qui suis-je ?</h1>
        <b-card
          title="Louis Christ"
          img-src="https://placekitten.com/300/300"
          img-alt="profile-picture"
          img-left
        >
          <b-card-text>
            Je me nomme
            <strong>
              Louis Christ
            </strong>
            et {{ status }}
          </b-card-text>
          <b-card-text>
            Ma principale passion est de découvrire les choses, apprendre une
            nouvelle technologie, des nouveaux language, de nouvelles méthodes
            de faire et défenseur de l'egoless programming.
          </b-card-text>
        </b-card>
      </div>

      <div id="studies" class="p-3">
        <h1>Mon Parcours</h1>
        <b-card no-body>
          <b-tabs card justified>
            <b-tab no-body active>
              <template v-slot:title>
                Etudes
                <b-badge variant="secondary">2</b-badge>
              </template>
              <b-tabs
                justified
                nav-class="subtabs"
                active-nav-item-class="subtabs-active"
              >
                <b-tab title="BAC" active>
                  <b-card-body>
                    Bac S mentions assez bien et mention Européenne (Anglais)
                  </b-card-body>
                </b-tab>
                <b-tab title="Epitech" active>
                  <b-card-body>
                    Diplôme d'ingénieurie en informatique en 5 ans (RNCP Niveau
                    1)
                  </b-card-body>
                </b-tab>
              </b-tabs>
            </b-tab>
            <b-tab title="Expériences pro" no-body>
              <template v-slot:title>
                Experience pro
                <b-badge variant="secondary">3</b-badge>
              </template>
              <b-tabs
                justified
                nav-class="subtabs"
                active-nav-item-class="subtabs-active"
              >
                <b-tab title="PumpMyKins" active>
                  <b-card-body>
                    Développement d'un site Web pour une association, gestion de
                    la trésorie de l'association.
                  </b-card-body>
                </b-tab>
                <b-tab title="Tra-Diction" active>
                  <b-card-body>
                    Maintenance d'un site web construit avec Symfoni
                  </b-card-body>
                </b-tab>
                <b-tab title="NoParking" active>
                  <b-card-body>
                    Débuggage et amélioration continue de l'application web
                    Opentime, application de gestion de temps et d'activités
                  </b-card-body>
                </b-tab>
              </b-tabs>
            </b-tab>
          </b-tabs>
        </b-card>
      </div>

      <div id="my-creations" class="p-3">
        <h1>Mes créations</h1>
        <b-card-group deck>
          <b-card
            title="PumpMyKins"
            img-src="https://picsum.photos/300/300/?image=42"
            img-alt="pumpmykins-logo"
            img-top
          >
            <b-card-text>
              Association a but non-lucratif proposant des serveurs de jeux
              multijoueurs. Projet réalisé à deux avec une équipe de bénévoles
              pour monitorer les serveurs.
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted">Intérompue en Janvier 2019</small>
            </template>
          </b-card>
          <b-card
            title="Mysh"
            img-src="https://picsum.photos/300/300/?image=41"
            img-alt="terminal"
            img-top
          >
            <b-card-text>
              Développement d'un shell basé sur tcsh avec un maximum de
              fonctionnalité, projet réaliser en équipe de 4 dans le cadre de
              mon diplôme.
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted">Terminé en Avril 2020</small>
            </template>
          </b-card>
          <b-card
            title="OS S"
            img-src="https://picsum.photos/300/300/?image=43"
            img-alt="Image"
            img-top
          >
            <b-card-text>
              L'OS S (OSS) avec un OS ne se basant sur aucun noyau, l'objectif
              étant de s'introduire au développement bas-niveau avec un minimum
              de librairie externe.
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted">Commencé en 2019 - En cours</small>
            </template>
          </b-card>
        </b-card-group>
      </div>

      <div id="contact-me" class="p-3">
        <h1>Me contacter</h1>
        <b-card>
          <template v-slot:header>
            <h4 class="mb-0">Formulaire de contact</h4>
          </template>
          <b-form @submit="onSubmit" @reset="onReset">
            <b-form-group
              id="input-email"
              label="Adresse Email:"
              label-for="input-email"
            >
              <b-form-input
                id="input-email"
                v-model="form.email"
                type="email"
                required
                placeholder="email@domain.fr"
              >
              </b-form-input>
            </b-form-group>

            <b-form-group
              id="input-name"
              label="Votre nom/prénom:"
              label-for="input-name"
            >
              <b-form-input
                id="input-name"
                v-model="form.name"
                required
                placeholder="Henry Dupont"
              >
              </b-form-input>
            </b-form-group>

            <b-form-group
              id="input-phone"
              label="Votre téléphone:"
              label-for="input-phone"
            >
              <b-form-input
                id="input-phone"
                v-model="form.phone"
                required
                placeholder="0304050608"
              >
              </b-form-input>
            </b-form-group>

            <b-form-group
              class="mb-0"
              label="Votre message:"
              label-for="message"
            >
              <b-form-textarea
                id="message"
                v-model="text1"
                placeholder="Entrez votre message"
                rows="10"
              ></b-form-textarea>
            </b-form-group>
            <b-button type="submit" variant="primary">Envoyer</b-button>
            <b-button type="reset" variant="danger">
              Vider le formulaire
            </b-button>
          </b-form>
        </b-card>
      </div>
    </div>
    <div class="lc-footer">
      <b-row class="text-center bg-dark text-light">
        <b-col class="p-3">Made by Louis Christ</b-col>
        <b-col class="p-3">Build with NuxtJS</b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: '',
        name: '',
        phone: '',
        checked: [],
      },
      show: true,
    }
  },
  computed: {
    status() {
      const now = new Date()
      const year = now.getFullYear() - 2019
      const month = now.getMonth()
      if (year < 5) {
        const str =
          'je suis en ' +
          (year + (month > 6 ? 1 : 0)) +
          'ème année à Epitech Lille'
        return str
      } else {
        return "diplomé d'Epitech depuis 2024"
      }
    },
  },
}
</script>
