<template>
    <h5></h5>
    <div class="container">
        <div class="row"> 
            <div class="shadow rounded">
                <form action="" @submit.prevent="signup">
                    <input type="text" class="form-control my-2" placeholder="Name" v-model="name" />
                    <input type="email" class="form-control my-2" placeholder="Email" v-model="email" />
                    <input type="number" class="form-control my-2" placeholder="Phone Number" v-model="phonenumber" />
                    <input type="password" class="form-control my-2" placeholder="Password" v-model="password" />
                    <p>I agree with <a href="">Terms and Conditions</a><span><input type="checkbox" v-model="terms"></span></p>
                    <button :disabled="!terms" type="submit" class="btn btn-dark mx-auto my-2"> Submit </button>
                </form>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from "vue";

    const name= ref("");
    const email = ref("");
    const phonenumber = ref("");
    const password = ref("");
    const terms = ref(false);

   const signup = ()=>{
        let obj = {name, email, phonenumber, password, terms}
        console.log(obj);
         localStorage.setItem('form1', JSON.stringify(obj));
    }
</script>