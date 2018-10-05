<template>
  <v-footer class="footer">

    <div class="left">
      &copy; 2018 by Paul Werner
    </div>
    <div class="buttons">
      <button class="button" @click="state.dialog.disclaimer = true">disclaimer</button>
      <button class="button" @click="state.dialog.legal = true">legal</button>
      <button class="button" @click="state.dialog.privacy = true">privacy</button>
    </div>

    <div class="right">
      <a href="https://www.giphy.com">
        <img src="../assets/giphy_powered_by.png">
      </a>
    </div>

    <div class="text-xs-center">

      <!-- DISCLAIMER -->
      <v-dialog
        v-model="state.dialog.disclaimer"
        width="600px">
        <v-card>

          <v-card-title
            class="headline grey lighten-2"
            primary-title
          >
            Disclaimer
          </v-card-title>


          <v-card-text>
            <p>
              The information on this Website is for general information purposes only.
              Paul Werner assumes no responsibility for errors or omissions in the contents
              of this Website.
            </p>

            <p> Paul Werner also reserves the right to make additions, deletions, modifications to the
              contents of the Website or even shut down the Website at any time without prior notice.
            </p>

            <p>
              Paul Werner does not guarantee that the Website is free of viruses or other harmful components.
            </p>

            <p>
              The Website contains links to external websites. Paul Werner is not liable or responsible for
              these external websites and contents. Should you have questions about these external websites,
              please direct them to the respecting providers.
            </p>
            <p>
              Icons made by <a href="https://www.flaticon.com/authors/appzgear" title="Appzgear">Appzgear</a> from <a
              href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a> is licensed by <a
              href="http://creativecommons.org/licenses/by/3.0/" title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a>
            </p>

            <span>Last updated: October 05, 2018</span>
          </v-card-text>
          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <button @click="state.dialog.disclaimer = false">close</button>
          </v-card-actions>
        </v-card>
      </v-dialog>

      <!-- LEGAL -->
      <v-dialog v-model="state.dialog.legal" width="600px">
        <v-card>
          <v-card-title
            class="headline grey lighten-2"
            primary-title
          >
            Legal
          </v-card-title>

          <v-card-text>
            <div>
              <p>Information pursuant to sec. 5 German Telemedia Act</p>
              <p>
                Paul Werner<br/>
                Holstenstr. 111<br/>
                22767 Hamburg</p>
              <p>
                email: contact@paulwerner.org
              </p>
              <p>
                The content and works on this website (“Website”) are subject to German
                copyright law. The reproduction, processing, distribution and any kind
                of exploitation outside the limits of copyright require the written consent
                of Paul Werner or the respective author.
              </p>
            </div>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <button @click="state.dialog.legal = false">close</button>
          </v-card-actions>
        </v-card>
      </v-dialog>

      <!-- PRIVACY -->
      <v-dialog v-model="state.dialog.privacy" width="600px">
        <v-card>
          <v-card-title
            class="headline grey lighten-2"
            primary-title
          >
            Privacy
          </v-card-title>

          <v-card-text>
            <p>
              Controller of this website (“Website”) pursuant to the General Data Protection
              Regulation (“GDPR”) is Paul Werner.
            </p>
            <p>
              When you visit this Website your IP address of the requesting computer, date and
              time of access, name and URL of the retrieved file, website from which the access
              is made (referrer URL), and the browser used and, if applicable, the operating
              system of your computer and the name of your access provider are collected and
              processed. These data are processed to ensure a smooth connection setup of the
              website, a comfortable use of the Website, evaluation of system security and stability
              and for other administrative purposes. The legal basis for processing is
              Art. 6 (1) f) GDPR. The data is deleted as soon as it is not longer needed for the
              above mentioned purposes.
            </p>
            <p>
              When you contact Paul Werner via the above mentioned email, your email address and the
              personal data you might mention in it are processed for the purpose of answering you
              and/or responding to your corresponding request
            </p>
            <p>
              As a data subject you have the rights pursuant to chapter 3 <br> (Art. 12 – 23) GDPR.
            </p>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <button @click="state.dialog.privacy = false">close</button>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>

  </v-footer>
</template>

<script>
  export default {
    name: 'Footer',
    data () {
      return {
        state: {
          fixed: false,
          dialog: {
            disclaimer: false,
            privacy: false,
            legal: false
          }
        }
      }
    }
  }
</script>

<style scoped>

  button:focus {
    cursor: pointer;
    outline: none;
  }

  .button {
    padding: 3px;
  }

  .buttons {
    right: 15px;
    padding: 5px;
  }
  .footer {
    color: #404040;
    padding: 5px;
    position: fixed;
    width: 100%;
    bottom: 0;
  }

  .right {
    position: absolute;
    right: 0;
    padding: 10px;

  }


</style>
