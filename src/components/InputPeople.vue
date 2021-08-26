<template>
<div>
    <form class ="amount">
        <div class = "form-control">
            <label> Number of People </label> <br>
            <input class= "person" type="number" :placeholder= 0 v-model.number="model"/> 
        </div>
    </form>
</div>
</template>

<script>
export default {

    name: 'InputPeople',

    props: {
        value:{
            type: Number,
            default:null
        }
    },
    data(){
        return {
            model: this.value
        }
    },

    watch: {
        model(currentValue){
            this.$emit('input', currentValue)
        }
    }
}

</script>

<style scoped>

.form-control {
    margin: 20px 0px;
}

.form-control label {
    font-size:13px;
    font-weight: 700;
    margin: 8px;
    color: hsl(186, 14%, 43%);
}

.form-control input {
    font-family: 'Space Mono', monospace;
    width: 90%;
    height: 40px;
    margin: 8px;
    padding: 4px 12px;
    font-size: 24px;
    font-weight: 700;
    color:hsl(183, 100%, 15%);
    border-radius: 4px;
    border: none;
    background-color: hsl(189, 41%, 97%);
    text-align: right;
}

.form-control > input:focus {
    outline: 2px solid hsl(172, 67%, 45%);

}

.person {
    background-image: url("../assets/images/icon-person.svg");
    background-position: left center;
    background-position-x: 5%;
    background-size: 11px;
    background-repeat: no-repeat;
}

/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* this is for Firefox */
input[type=number] {
  -moz-appearance: textfield;
}

</style>



