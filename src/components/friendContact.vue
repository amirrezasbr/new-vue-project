<template>
  <li>
    <h2>{{ name }} {{ friendIsFavorite === '1'? '(favorite)':''  }}</h2>
    <button @click="toggleFavorites">toggle favorite</button>
    <button @click="toggleDetails">{{ detailsAreVisible? 'hide':'Show Details'  }}</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone:</strong>{{ phoneNumber }}</li>
      <li><strong>Email:</strong>{{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
    props:[
        'name',
        'phoneNumber',
        'email',
        'isFavorite',
    ],
    data(){
        return{
            detailsAreVisible:false,
            friendIsFavorite: this.isFavorite,
        }
},
methods:{
    toggleDetails(){
        this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorites(){
        console.log(this.friendIsFavorite )
        if(this.friendIsFavorite === '1'){
            this.friendIsFavorite = '0'; 
        }else{
            this.friendIsFavorite = '1'; 
        }
    }
}
}
</script>

<style></style>
