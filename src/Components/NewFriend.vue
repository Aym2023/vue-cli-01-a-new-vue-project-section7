<template>
    <form @submit.prevent='submitData'>
        <div>
        <label for="name">Name</label>
        <input type="text" v-model='enteredName'/>
        </div>
        <div>
        <label for="phone">Phone</label>
        <input type="tel" v-model='enteredPhone'/>
        </div>
        <div>
        <label for="email">Email</label>
        <input type="email" v-model='enteredEmail'/>
       </div>
     <button>Add Contact</button>
    </form>
</template>

<script>
export default {
    emits: ['add-contact'],
    data() {
     return {
        enteredName: '',
        enteredPhone: '',
        enteredEmail: '',
     };
    },
    methods: {
        submitData() {
            this.$emit('add-contact' ,
            this.enteredName,
            this.enteredPhone,
            this.enteredEmail
        );      
        },
    },
};
</script>

<style>
#app input {
    font: inherit;
    padding: 0.15rem;
  }
  #app label {
    font-weight: bold;
    margin-right: 1rem;
    width: 7rem;
    display: inline-block;
  }
  #app form div {
    margin: 1rem 0;
  }
  </style>