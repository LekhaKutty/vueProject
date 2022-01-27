<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}" >
          <slot></slot> 
          <div class="actions">
            <slot name = "linksToModal"></slot>
          </div>           
        </div>
    </div>
</template>

<script>
export default {
    props: ['theme'],
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
    color:  rgb(29, 3, 3);
    border: none;
    padding: 0;
  }
  .modal p {
    font-style: normal;
  }
  .modal.sale h1,p{
    color:  rgb(29, 3, 3);
  }
  .modal.sale{
    background: rgb(138, 39, 39);
  }
  .modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
    color:  #eee;
  }
  .modal .actions a {
    
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
  }
  

</style>