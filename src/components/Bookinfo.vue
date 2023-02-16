<script>
export default{
    data(){
        return{
            detailsAreVisible:false,
            book:
                {
                    id:1,
                    title:"Orgullo y prejuicio",
                    author:"Jane Austin",
                    realseDate:"1813-01-28",
                    img:'orgullo.jpg'
                }
                                   
        };
    },

    methods: {
        toggleDetails(){
            this.detailsAreVisible = !this.detailsAreVisible;
        },
        getImgUrl(){
            return this.book.img;
        }
    },
}
</script>


<template>

 <li class="lista">
    <h1>{{book.author}}</h1>
     <button type="button" @click="toggleDetails">{{detailsAreVisible ? "Hide":"Show"}}</button>
    <ul v-if="detailsAreVisible">
    <li><strong>Author:</strong>{{book.author}}</li>
    <li><strong>Realse Date:</strong>{{book.realseDate}}</li>
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