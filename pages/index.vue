<template>
  <v-layout>
    <v-flex class="text-center">
      <v-row justify="center">
        <v-dialog v-model="dialog" width="600px">
          <template v-slot:activator="{ on }">
            <v-btn color="primary" dark v-on="on">Check type</v-btn>
          </template>
          <v-card>
            <v-card-title>
              <span class="headline">Blood type {{type}} detected</span>
            </v-card-title>
            <v-card-text>Xin chào {{name}}, bạn sinh năm {{year}} Nhóm máu của bạn là nhóm máu {{type}}
             btw, Ai lấy đồ ăn của a Jesse thì nhận đi =.=</v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="green darken-1" text @click="dialog = false">Chuẩn vãi</v-btn>
              <v-btn color="green darken-1" text @click="dialog = false"> Chuẩn Ghê</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-row>
      <v-form>
        <v-container>
          <v-row>

            <v-col cols="12" sm="6">
              <v-text-field
                v-model="name"
                label="Họ tên"
                outlined
              ></v-text-field>
            </v-col>

            <v-col cols="12" sm="6">
              <v-text-field
                v-model="year"
                label="Ngày sinh"
                outlined
              ></v-text-field>
            </v-col>

            <v-col cols="12" sm="6">
              <v-text-field
                v-model="type"
                label="Nhóm máu"
                outlined
              ></v-text-field>
            </v-col>

          </v-row>
        </v-container>
      </v-form>
    </v-flex>
  </v-layout>
</template>
<script>
  export default {
      data: () => ({
          dialog : false,
          name: '',
          year: '',
          type: ''
      })
      ,
      method: {
          open(){
              this.dialog = true
          }
      }
  }
  </script>
