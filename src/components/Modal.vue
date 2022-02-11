
<template>
    
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="theme ? 'dark' : 'sale' ">
            <h1>{{title}}</h1>
            <h4>{{header}}</h4>
            <h5>{{text}}</h5>
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>

</template>

<script>
    export default ({
    props:['title','header', 'text', 'theme'],
    methods: {
        closeModal(){
            this.$emit('close')
        }
    },
  
    })
</script>


<style scoped>
h1{
    color: rgb(8, 235, 117);
}

.modal{
    width :400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.modal .actions {

    text-align: center;
    margin: 40px 0 40px 0;
    color: rgb(129, 23, 23);
}
.modal .actions .a{

    padding: 8px;
    border:1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin:10px;
}
.backdrop{
    top:0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
.sale{
    border: 2px solid  rgb(218, 17, 10);
    border-style:dashed;
    color: rgb(216, 214, 230);
}
.dark{
    background: black;
    color: rgb(209, 197, 178);
    
}


</style>