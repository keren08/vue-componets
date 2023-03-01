<script>
export default{
  props: {
    id:{
    type:String,
    required :true
    },
    title:{
    type:String,
    required :true
    },
    author:{
    type:String,
    required :true
    },

    realseDate:{
    type:String,
    required :true
    },
    isLike:{
    type:String,
    required :false,
    default:'0',
    validator: function(value){
      return value ==="1"|| value==="0";
    }
    }
    },
    data(){
        return{
            detailsAreVisible:false,
            bookIsLike: this.isLike,
                                   
        };
    },

    methods: {
        toggleDetails(){
            this.detailsAreVisible = !this.detailsAreVisible;
        },
      toggleFavorites(){
        if(this.bookIsLike==='1'){
          this.bookIsLike ='0';
        }else{
          this.bookIsLike ='1';
        }
      }
    },
}
</script>


<template>

 <li class="lista">
    <h1>{{title}}{{bookIsLike ==='1'?"(like)":''}}</h1>
     <button type="button" @click="toggleDetails">{{detailsAreVisible ? "Hide":"Show"}}</button>
    <button type="button" @click="toggleFavorites">Favorite</button>
    <ul v-if="detailsAreVisible">
    <li><strong>Author:</strong>{{author}}</li>
    <li><strong>Realse Date:</strong>{{realseDate}}</li>
    </ul>
 </li>

</template>


<style>
  h1{
    font-size: 2rem ;
  }

  .lista{
    border: 1px dashed white;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  li{
    list-style: none;
  }

</style>