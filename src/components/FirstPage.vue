<template>
    <v-app class="background">
        <v-container class="d-flex justify-center align-center" style="height: 100vh;">
            <v-card class="mx-auto" outlined>
                <v-card-text class="text-h5">
                    {{ randomPhrase }}
                </v-card-text>
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
        "Doubt thou the stars are fire, Doubt that the sun doth move, Doubt truth to be a liar, But never doubt I love",
        "Hear my soul speak. Of the very instant that I saw you, Did my heart fly at your service",
        "You are the bane of my existence and the object of all my desires.",
        "I Burn for You",
        "I love all of you. Even the parts that you believe are too dark and too shameful. Every scar. Every flaw. Every imperfection. I love you",
        "I want a life that suits us both. I know I am imperfect, but I will humble myself before you because I cannot imagine my life without you",
        "I cannot stop thinking of you. From the mornings you ease to the evenings you quiet, to the dreams you inhabit... My thoughts of you never end. I am yours. I have always been yours.",
        "And in fact, preferring sleep because that is where I might find you",
        "You occupy my every thought.",
        "I know you will lift my spirits and make me see the world in ways I could not have imagined.",
        "True love is something else entirely. It is when the rest of the world goes quiet. It is not eyes that meet, but souls that dance. Settle into each other. Make room for each other. Until there is nowhere else to hide.",
        "I have not been able to sleep, not been able to eat. I can barely speak these days. My entire thoughts consumed by. By our kiss. By you.",
        "I don't need to understand the plan! I trust my love.",
        "I saw that you were perfect, and so I loved you. Then I saw that you were not perfect and I loved you even more",
        "To the world you may be one person, but to one person you are the world",
        "I need you like a heart needs a beat.",
        "If I had a flower for every time I thought of you...I could walk through my garden forever",
        "I love you for all that you are, all that you have been and all that you will be",
        "You are the best thing that's ever been mine",
        "You make me want to be a better woman.",
        "I never want to stop making memories with you.",
        "Your hand touching mine. This is how galaxies collide.",
        "To be your friend was all I ever wanted; to be your lover was all I ever dreamed.",
        "Take my hand, take my whole life too. For I can't help falling in love with you.",
        "And in his smile I see something more beautiful than the stars.",
        "Because of you, I can feel myself slowly, but surely, becoming the me I have always dreamed of being.",
        "Our love is like the wind. I can't see it, but I can feel it",
        "I love that you are the last person I want to talk to before I go to sleep at night.",
        "He's more myself than I am. Whatever our souls are made of, his and mine are the same.",
        "I want all of you, forever, you and me, every day.",
        "I can't see anything I don't like about you.",
        "To me, you are perfect.",
        "You had me at hello.",
        "I love you. You complete me",
        "Kiss me. Kiss me as if it were the last time",
        "I like you very much. Just as you are.",
        "You want the moon? Just say the word, and I'll throw a lasso around it and pull it down",
        "I think I'd miss you even if we'd never met",



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
    
    .v-card-text {
        text-overflow: ellipsis;
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
  