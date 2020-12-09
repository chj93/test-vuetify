<template>

  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>logo</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text rounded>Home</v-btn>
      <v-btn text rounded>Login</v-btn>
    </v-app-bar>
    <!--content로 요소가 겹치지 않도록-->
    <v-content>
      <!-- class="mt-5 mx-a" ==여백 상단 10, 가로여백 자동-->
      <v-card width="400" class="mx-auto mt-15">
        <!--class="pb-0 padding-bottom:0px " -->
        <v-card-title class="pb-0">
          <h1>Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form>
            <!--prepend- 입력칸 전에 표시될 아이콘, append - 입력칸 끝에 표시될 아이콘 -->
            <v-text-field label="Username"
              prepend-icon="mdi-account-circle"

            />
            <!--3항 연산자로 showPassword의 값을 이용해 이미지, input type 설정  -->
            <v-text-field
                    v-bind:type="showPassword? 'text':'password'"
                    label="Password"
                    prepend-icon="mdi-lock"
                    :append-icon="showPassword?'mdi-eye':'mdi-eye-off'"
                    @click:append="showPassword = !showPassword"
            />
          </v-form>
        </v-card-text>
        <v-divider></v-divider> <!-- hr tag-->
        <v-card-actions>
          <v-btn color="success">Register</v-btn>
          <v-spacer></v-spacer><!--공간 추가-->
          <v-btn color="info">Login</v-btn>
        </v-card-actions>
      </v-card>
    </v-content>

    <v-footer color="primary lighten-1" padless>
      <v-layout justify-center wrap>
        <v-btn
                v-for="link in links"
                :key="link"
                color="white"
                text
                rounded
                class="my-2"
        >
          {{ link }}
        </v-btn>
        <v-flex primary lighten-2 py-4 text-center white--text xs12>
          {{ new Date().getFullYear() }}—<strong>Vuetify</strong>
        </v-flex>
      </v-layout>
    </v-footer>

  </v-app>

</template>

<script>

export default {
  name: 'App',

  components: {

  },

  data: () => ({
    showPassword:false,
    links:[
      'Home','Login'
    ]
  }),
};
</script>
