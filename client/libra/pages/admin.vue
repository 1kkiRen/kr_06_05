<template>
    
    <div>
        {{ items }}
    </div>
    
</template>

<script>
export default {
    data(){
        return{
            id: '',
            title: '',
            author: '',
            items: [],
        }
    },

    mounted(){
        this.$axios.get('http://127.0.0.1:8000/api/book/all')
        .then(req => {   
            this.items = req.data ;                    
            console.log(req.data);
        })
    }

}
</script>