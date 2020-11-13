<template>
  <div class="newPost">
    <h3>I tuoi post</h3>
    <ul>
      <li v-for="(p, i) in posts" :key="i">
        {{ p.title }}
      </li>
    </ul>
    <button @click="$refs.modalName.openModal()">Open modal</button>
    <modal ref="modalName">
      <template v-slot:header>
        <h1 class="modal">Modal Posts</h1>
      </template>

      <template v-slot:body>
        <ul>
          <li v-for="(p, i) in posts" :key="i">
            <h1>{{ p.title }}</h1>
            <p>{{ p.text }}</p>
          </li>
        </ul>
      </template>

      <template v-slot:footer>
        <div>
          <button @click="$refs.modalName.closeModal()">X</button>
        </div>
      </template>
    </modal>
  </div>
</template>

<script>
import { EventBus } from "../main.js";
import Modal from "../components/Modal";

export default {
  name: "list",
  components: {
    Modal,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title:
            "Liguria, Toscana, Abruzzo, Basilicata e Umbria saranno “area arancione”",
          text:
            "Dal prossimo mercoledì Liguria, Toscana, Abruzzo, Basilicata e Umbria saranno considerate “area arancione”: saranno quindi inserite nella fascia intermedia di rischio coronavirus prevista dall’ultimo Dpcm e i loro abitanti saranno soggetti a restrizioni maggiori. La decisione sarà contenuta in un’ordinanza che il ministro della Salute Roberto Speranza dovrebbe firmare lunedì sera, ma è già stata annunciata dal presidente della regione Abruzzo Marco Marsilio, informato dal ministro Speranza. Il provvedimento sarà valido per due settimane.",
        },
        {
          id: 2,
          title: "A chi non piace la vittoria di Biden",
          text:
            "Dopo la vittoria di Joe Biden alle elezioni americane, la maggior parte dei leader mondiali ha fatto le congratulazioni al presidente eletto. Quelle di Angela Merkel, Emmanuel Macron e Justin Trudeau sono arrivate pochi minuti dopo che i network avevano annunciato che Biden aveva superato la soglia necessaria di grandi elettori. Altri leader mondiali, invece, hanno preferito aspettare. Alcuni ci hanno messo qualche ora a congratularsi con Biden, altri qualche giorno, altri non l’hanno ancora fatto. Molti di questi leader riluttanti guidano paesi che, per una molteplicità di motivi, hanno ragioni per essere scontenti dell’elezione del candidato del Partito democratico, e che probabilmente faticheranno nei rapporti con la nuova amministrazione.",
        },
        {
          id: 3,
          title: "Come riconoscere le recensioni false su Amazon",
          text:
            "I primi di settembre Amazon ha cancellato dalla sua piattaforma circa 20mila recensioni tra quelle scritte da sette degli utenti più attivi nel Regno Unito. L’ha fatto perché era uscita un’indagine del Financial Times che dimostrava che questi utenti venivano pagati dai venditori per scrivere recensioni positive ai loro prodotti. Tra gli altri, il Financial Times aveva raccontato la storia di Justin Fryer, il primo degli utenti britannici di Amazon per numero di recensioni fatte, che riceveva prodotti in regalo da piccoli marchi cinesi, li valutava con cinque stelle e poi li rivendeva su eBay. Da giugno a settembre era riuscito a guadagnare in questo modo circa 20mila sterline.",
        },
        {
          id: 4,
          title: "Il vaccino di Pfizer sembra più efficace del previsto",
          text:
            "Il vaccino sperimentale contro il coronavirus sviluppato dall’azienda farmaceutica statunitense Pfizer, in collaborazione con la tedesca BioNTech, ha dato risultati sopra le aspettative, rivelandosi più efficace di quanto atteso. La notizia segna un importante progresso nelle sperimentazioni dei vaccini per contenere la pandemia, ma saranno ancora necessari test e verifiche per assicurarsi che la soluzione sviluppata da Pfizer sia efficace nel medio termine e sicura.",
        },
      ],
    };
  },
  created() {
    EventBus.$on("addPost", (p) => {
      p.id = Math.floor(Math.random() * 100) + 1;
      this.posts.push(p);
      console.log(this.posts);
    });
  },
};
</script>

<style>
h1.modal {
  margin: 10px auto;
}
.overflow-hidden {
  overflow: hidden;
}
li {
  list-style: none;
  text-align: left;
  padding: 15px;
  border: 1px solid rgba(169, 169, 169, 0.5);
}
li:hover {
  background-color: rgba(169, 169, 169, 0.3);
}
.modal__body li {
  border: none;
}
@media screen and (max-width: 396px) {
  .modal__body h1 {
    font-size: 29px;
  }
}
</style>