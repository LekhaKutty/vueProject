<template>
    <div class="backdrop" >
        <div class="modal" :class="{ sale: theme === 'sale'}" >
            <h1>{{ header }}</h1>
            <p>{{text}}</p>
            <button @click="closeModal">Close Modal</button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header','text', 'theme'],
    methods: {
        closeModal() {
            this.$emit('passToggleModalfromApp')
        }
    }
}
</script>


<style>
 .modal {
    width: 400px;
    padding: 20px;
    margin: 200px auto;
    background: white;
    border-radius: 10px;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
  }
  .modal h1 {
    color: #03cfb4;
    border: none;
    padding: 0;
  }
  .modal p {
    font-style: normal;
  }
  .modal.sale h1,p{
    color: rgb(9, 38, 65);
  }
  .modal.sale{
    background: rgb(138, 39, 39);
  }
  

</style>