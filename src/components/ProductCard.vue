<template>
    <div class="container ">

<div class="row">
    <h4>Productos relacionados</h4>
</div>
<div class="row">
    <div v-for="(producto, indice) of productos" :key="indice"  class="col">
        <div class="col">
            <div class="card" style="width: 18rem;">
                <div class="card-body">
                    <h5 class="card-title">{{ producto.nombre }}</h5>
                    <img class="img-fluid" :src="producto.imagen" alt="" >
                    <p class="card-text"> {{ producto.descripcion }}</p>
                        <div class="producto-relacionado-precio">Precio:{{ producto.precio }} BOB</div>
                    <div>
            <div >
                <div v-for="(color, indice) of producto.colores" :key="indice" class="color-box" :style="`background:${color}`"></div>
            </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</div>
</template>

<script>
export default {
    name: 'ProductCard',
    props: {},
    emits:[],
    data() {
        return {
            productos:[]
        }
    },
    methods: {
        getProducto(){
            this.axios.get("http://localhost:5000/Productos")
                .then((response)=>{this.productos = response.data})
                //.then((response)=>{console.log(response.data)})
                .catch((e)=>{console.log(e)})
        }
    },
    computed:{},
    mounted(){
        this.getProducto();
    },
    components:{

    }
}
</script>
<style scoped>
 .color-box {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin: 7px;
    display: inline-block;
            }
.container{
    margin-top: 50px;
}
.producto-relacionado-precio{
                background: orangered;
                color: white;
                text-align: center;
                padding: 10px; 
            }
</style>