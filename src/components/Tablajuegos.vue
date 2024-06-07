<template>
    <div class="juegos">
        <main class="container">
            <section class="lista-productos">
                <table class="table">
                    <thead>
                        <tr>
                            <th scope="col">Código</th>
                            <th scope="col">Nombre</th>
                            <th scope="col">stock</th>
                            <th scope="col">Precio</th>
                            <th scope="col">Acciones</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(juego, index) in listaJuegos" :key="index">
                            <th scope="row">{{ juego.codigo }}</th>
                            <td>{{ juego.nombre }}</td>
                            <td>{{ juego.stock }}</td>
                            <td>{{ juego.precio }}</td>
                            <td>
                                <button class="btn btn-success mx-1" @click="botonAddStock(juego.codigo)">+</button>
                                <button class="btn btn-danger mx-1" @click="botonDeleteStock(juego.codigo)">-</button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </section>

        </main>
    </div>

</template>


<script>
import { mapActions, mapState } from "vuex";
export default {
    name: "TablaJuegos",
    components: {
    },
    data() {
        return {

        }
    },
    computed: {
        ...mapState(["listaJuegos"]),

    },
    methods: {
        ...mapActions(["cargarJuegos"]),
        botonAddStock(codigo) {
            this.$store.dispatch("addStock", codigo)
        },
        botonDeleteStock(codigo) {
            this.$store.dispatch("deleteStock", codigo)
        },
    },
    async created() {
        try {
            let respuesta = await this.cargarJuegos();
            if (!respuesta) {
                this.error = "No se cargaron los Juegos";
            }
        } catch (error) {
            this.error = "Algo salió mal al intenar cargar Juegos"
        }
    }
}
</script>


<style scoped lang="scss">
.table {
    &__img {
        width: 100px;
        aspect-ratio: 1/1;
    }

    td,
    th {
        vertical-align: middle;
        text-align: center;
    }
}

.form-add-producto {
    &__wrapper-form {
        padding: 15px 0px;
    }
}
</style>