<template>
    <q-btn flat round dense icon="mdi-chat" @click="dialog = true">
         
         <q-dialog
          v-model="dialog"
          persistent
          :maximized="maximizedToggle"
          transition-show="slide-up"
          transition-hide="slide-down">      
          
          <q-card class="bg-teal-10 text-white">
          <div class="drawer"><DrawerChat/></div>
          <q-bar>
          <h5>Chat</h5>
          <q-space />
          <q-btn dense flat icon="close" v-close-popup>
          <q-tooltip class="bg-white text-primary">Close</q-tooltip>
          </q-btn>
         
          </q-bar>
        
        <q-toolbar class="chat bg-grey-3 text-black ">
          
          <q-btn round flat icon="insert_emoticon" class="q-mr-sm" />
          <q-input rounded outlined dense class="WAL__field col-grow q-mr-sm" bg-color="white" v-model="message" placeholder="Type a message" />
          <q-btn round flat icon="send" />
        </q-toolbar>
    
      </q-card>
    
    </q-dialog>
 </q-btn>
</template>
<style scoped>

.q-dialog__inner--maximized > div {
    width: 80%;
    height: 80%;

}

.chat{
width: 100%;
height: 20%;
background-color: red;
 
}
.drawer{
    width: 25%;
    height: 100%;
    background-color: white;
    color:#000 ;
}
</style>
<script setup>
import { ref } from 'vue'
import DrawerChat from 'src/components/DrawerChat.vue'

const text = ref('')
const dialog = ref(false)
const maximizedToggle = ref(true)

</script>