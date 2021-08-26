<template>

    <form class ="answers">
        <div class = "form-output">
            <label> {{text}} 
                <p>/person</p>
            </label>
            <div class="output" :name="text"> 
            ${{result.toFixed(2)}} || '0.00' }}
            </div>
        </div>
    </form>
</template>

<script>
export default {
    name: 'Result',
    
    props: {
        text: String,
        result: Number,
    },
}
</script>

<style scoped>
    .form-output {
        margin: 10px 0px;
        display: flex;
        padding-top: 24px;
    }
    .form-output label {
        padding-right: 60px; 
        padding-left: 30px;
        font-size: 13px;
        font-weight: 700;
        margin: 8px;
        color: hsl(189, 41%, 97%);
        width: 200px;
    }
    .form-output p {
        color: hsl(184, 14%, 56%);
        padding-left: 0px;
    }
    .output {
        font-family: 'Space Mono', monospace;
        overflow: hidden;
        text-align: right;
        width: 160px; 
        height: 40px;
        margin: 0px;
        padding-top: 0px;
        padding-right: 10px;
        margin-right: 24px;
        font-size: 32px;
        font-weight: 700;
        color:hsl(172, 67%, 45%);
        border-radius: 4px;
        border: 10px;
        background-color: hsl(183, 100%, 15%);
    }
/*
Light grayish cyan: hsl(185, 41%, 84%)
- Light grayish cyan: hsl(189, 41%, 97%)
*/
</style>