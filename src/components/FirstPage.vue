<template>
    <v-app class="background">
        <v-container class="d-flex justify-center align-center" style="height: 100vh;">
            <v-card class="mx-auto" outlined>
                <v-card-title class="text-h5">
                    {{ randomPhrase }}
                </v-card-title>
                <v-card-actions class="justify-center">
                    <v-btn class="custom-btn" @click="getRandomPhrase">More</v-btn>
                </v-card-actions>
            </v-card>
        </v-container>
    </v-app>
</template>
  
<script>
import { ref, onMounted } from "vue";

export default {
  setup() {
    // Stato reattivo
    const phrases = [
        "Life is what happens when you're busy making other plans.",
        "The greatest glory in living lies not in never falling, but in rising every time we fall.",
        "The way to get started is to quit talking and begin doing.",
        "Don't let yesterday take up too much of today.",
        "You only live once, but if you do it right, once is enough."
    ];
    const randomPhrase = ref("");

    // Metodo per selezionare una frase casuale
    const getRandomPhrase = () => {
      const randomIndex = Math.floor(Math.random() * phrases.length);
      randomPhrase.value = phrases[randomIndex];
    };

    // Inizializzazione con una frase casuale quando il componente viene montato
    onMounted(() => {
      getRandomPhrase();
    });

    // Esposizione delle variabili e metodi
    return {
      randomPhrase,
      getRandomPhrase
    };
  }
};
</script>

  
<style>
   .background {
        background-image: url('../assets/image1.jpg');
        background-size: cover; /* Adatta l'immagine per coprire l'intero sfondo */
        background-position: center;
    }
    .v-card-title {
        font-family: 'Playfair Display', serif; /* Un font elegante */
        font-size: 1.5rem; /* Dimensione del testo */
        color: #4a4a4a; /* Colore sofisticato, grigio scuro */
        text-align: center; /* Centrare il testo */
        line-height: 1.6; /* Migliora la leggibilità */
        text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2); /* Ombreggiatura per un tocco raffinato */
        padding: 16px; /* Spaziatura intorno al testo */
    }

    .custom-btn {
        font-family: 'Playfair Display', serif; /* Font elegante */
    }
</style>
  