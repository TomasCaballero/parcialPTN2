<template>
    <input type="text" v-model="texto" placeholder="Escribe algo aquí" class="mb-2 w-50" />
    <div class="card p-2 w-50">
        <p><strong>Cantidad de caracteres =</strong> {{ cantidadCaracteres }}</p>
    </div>
    <ol class="mb-4">
        <li>
            <p>{{ codificado() }}</p>
        </li>
        <li>
            <p>{{ toUpperCase() }}</p>
        </li>
        <li>
            <p>{{ toLowerCase() }}</p>
        </li>
        <li>
            <p>{{ minMay() }}</p>
        </li>
        <li>
            <p>{{ mayMin() }}</p>
        </li>
    </ol>

    <div class="card p-3 w-50">
        <p>Respuestas: 1:C - 2:C - 3:A</p>
    </div>
</template>

<script>
export default {
    name: 'Contenido',
    data() {
        return {
            texto: '',
        }
    },
    methods: {
        codificado() {
            const textoMinuscula = this.texto.toLowerCase();
            let resultado = '';

            for (let i = 0; i < textoMinuscula.length; i++) {
                const caracter = textoMinuscula[i];

                if (caracter === 'a') {
                    resultado += 'u';
                } else if (caracter === 'e') {
                    resultado += 'o';
                } else if (caracter === 'o') {
                    resultado += 'e';
                } else if (caracter === 'u') {
                    resultado += 'a';
                } else {
                    
                    resultado += caracter;
                }
            }
            return resultado;
        },
        toUpperCase() {
            return this.texto.toUpperCase();
        },
        toLowerCase() {
            return this.texto.toLowerCase();
        },
        minMay() {
            let resultado = '';

            for (let i = 0; i < this.texto.length; i++) {
                const caracter = this.texto[i];
                if (i % 2 === 0) {
                    resultado += caracter.toUpperCase();
                } else {
                    resultado += caracter.toLowerCase();
                }
            }
            return resultado;
        },
        mayMin() {
            let resultado = '';

            for (let i = 0; i < this.texto.length; i++) {
                const caracter = this.texto[i];
                if (i % 2 === 0) {
                    resultado += caracter.toLowerCase();
                } else {
                    resultado += caracter.toUpperCase();
                }
            }
            return resultado;
        }
    },
    computed: {
        cantidadCaracteres() {
            return this.texto.length;
        },
    }
}
</script>

<style scoped></style>