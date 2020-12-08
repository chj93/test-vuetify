<template>
  <v-app>
    <!-- class="mt-5 mx-a" ==여백 상단 10, 가로여백 자동-->
    <v-card width="400px" class="mt-10 mx-a">
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
          <v-text-field
                  :type="showPassword? 'text':'password'"
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
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {

  },

  data: () => ({
    showPassword:false
  }),
};
</script>
