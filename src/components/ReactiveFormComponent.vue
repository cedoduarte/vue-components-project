<template>
    <form class="reactive-form">
        <h1>Personal information</h1>
        <div class="form-group">
            <label for="firstName">First name</label>
            <input class="form-control" 
                   id="firstName" 
                   name="firstName" 
                   type="text" 
                   placeholder="Enter first name" 
                   v-model="formData.firstName" />
        </div>
        <div class="form-group">
            <label for="lastName">Last name</label>
            <input class="form-control"
                   id="lastName" 
                   name="lastName" 
                   type="text" 
                   placeholder="Enter last name"
                   v-model="formData.lastName" />
        </div>
        <div class="form-group">
            <label for="email">Email</label>
            <input class="form-control"
                   id="email" 
                   name="email" 
                   type="email" 
                   placeholder="Enter email"
                   v-model="formData.email" />
        </div>
        <div class="form-group">
            <label for="phoneNumber">Phone number</label>
            <input class="form-control"
                   id="phoneNumber" 
                   name="phoneNumber" 
                   type="text" 
                   placeholder="Enter phone number"
                   v-model="formData.phoneNumber" />
        </div>
        <div class="form-group">
            <label for="birthdate">Birthdate</label>
            <input class="form-control"
                   id="birthdate" 
                   name="birthdate" 
                   type="date" 
                   v-model="formData.birthdate" />
        </div>
        <div class="form-group">
            <label for="zipCode">Zip code</label>
            <input class="form-control"
                   id="zipCode" 
                   name="zipCode" 
                   type="text" 
                   placeholder="Enter zip code"
                   v-model="formData.zipCode" />
        </div>
        <div class="form-group">
            <label for="address">Address</label>
            <input class="form-control"
                   id="address" 
                   name="address" 
                   type="text" 
                   placeholder="Enter address"
                   v-model="formData.address" />
        </div>
        <div class="form-group">
            <label for="country">Country</label>
            <input class="form-control"
                   id="country" 
                   name="country" 
                   type="text" 
                   placeholder="Enter country"
                   v-model="formData.country" />
        </div>
        <div class="form-group">
            <label for="province">Province</label>
            <input class="form-control" 
                   id="province" 
                   name="province" 
                   type="text" 
                   placeholder="Enter province"
                   v-model="formData.province" />
        </div>
        <div class="form-group">
            <label for="city">City</label>
            <input class="form-control"
                   id="city"
                   name="city"
                   type="text"
                   placeholder="Enter city"
                   v-model="formData.city" />
        </div>
        <button class="btn"
                type="submit" 
                @click.prevent="formSubmitted">
            Send
        </button>
    </form>
    {{ formData }}
</template>

<script setup lang="ts">
import { reactive } from "vue";

const formData = reactive({
    firstName: "",
    lastName: "",
    email: "",
    phoneNumber: "",
    birthdate: "",
    zipCode: "",
    address: "",
    country: "",
    province: "",
    city: ""
});

const formSubmitted = () => {
    console.log(formData);
}
</script>

<style scoped>
.reactive-form {
    width: 500px;
    width: 50%; 
    margin: 0 auto;
}

.reactive-form div {
    margin-bottom: 5px;
}

.reactive-form button {
    background-color: cyan;
    border-width: 0;
    color: black;
}
</style>