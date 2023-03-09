<script>
  // @ts-nocheck

  import cpaLogo from "./assets/CycloPlomberie_LogoH.svg";
  // import svelteLogo from './assets/svelte.svg'
  // import Counter from "./lib/Counter.svelte";
  let count = 1;
  const increment = () => {
    count += 1;
  };
  const decrement = () => {
    count -= 1;
    etape.pop();
    etape = etape;

    // etape[count] = "";
  };
  $: etape = [];
  let etape1;
  let etape2;
  let etape3;
  let etape4;
  let etape5;
  let etape6;
  let goform = false;
  let level1 = [
    { id: "1-1", name1: "Dépannage", src: "/pictos/depannage.svg" },
    { id: "1-2", name1: "Pose", src: "/pictos/pose.svg" },
    { id: "1-3", name1: "Entretien", src: "/pictos/entretien.svg" },
  ];
  let level21 = [
    { id: "21-1", name1: "Fuite", src: "/pictos/fuite.svg" },
    {
      id: "21-2",
      name1: "Canalisation bouchée",
      src: "/pictos/canalisation-bouchee.svg",
    },
  ];
  let level22 = [
    {
      id: "22-1",
      name1: "Au sol",
      src: "/pictos/chaudiere-sol.svg",
      prix: "120",
    },
    {
      id: "22-2",
      name1: "Murale",
      src: "/pictos/chaudiere-murale.svg",
      prix: "70",
    },
  ];
  let level31 = [
    {
      id: "31-10",
      name1: "Arrivée d'eau",
      src: "/pictos/arrivee-eau.svg",
    },
    {
      id: "31-11",
      name1: "Canalisations",
      src: "/pictos/canalisation.svg",
    },
    { id: "31-1", name1: "Évier", src: "/pictos/evier.svg" },
    {
      id: "31-2",
      name1: "Lavabo",
      src: "/pictos/lavabo.svg",
    },
    {
      id: "31-3",
      name1: "Baignoire",
      src: "/pictos/baignoire.svg",
    },
    {
      id: "31-4",
      name1: "Douche",
      src: "/pictos/douche.svg",
    },
    {
      id: "31-5",
      name1: "WC classiques",
      src: "/pictos/wc.svg",
    },
    {
      id: "31-6",
      name1: "WC suspendues",
      src: "/pictos/wc-suspendus.svg",
    },
    {
      id: "31-7",
      name1: "Lave-linge",
      src: "/pictos/lave-linge.svg",
    },
    {
      id: "31-8",
      name1: "Lave-vaisselle",
      src: "/pictos/lave-vaisselle.svg",
    },
    {
      id: "31-9",
      name1: "Autres",
      src: "/pictos/autre.svg",
    },
  ];
  let level32 = [
    {
      id: "32-10",
      name1: "Canalisation",
      src: "/pictos/canalisation.svg",
    },

    { id: "32-1", name1: "Évier", src: "/pictos/evier.svg" },
    {
      id: "32-2",
      name1: "Lavabo",
      src: "/pictos/lavabo.svg",
    },
    {
      id: "32-3",
      name1: "Baignoire",
      src: "/pictos/baignoire.svg",
    },
    {
      id: "32-4",
      name1: "Douche",
      src: "/pictos/douche.svg",
    },
    {
      id: "32-5",
      name1: "WC classiques",
      src: "/pictos/wc.svg",
    },
    {
      id: "32-6",
      name1: "WC suspendues",
      src: "/pictos/wc-suspendus.svg",
    },
    {
      id: "32-7",
      name1: "Lave-linge",
      src: "/pictos/lave-linge.svg",
    },
    {
      id: "32-8",
      name1: "Lave-vaisselle",
      src: "/pictos/lave-vaisselle.svg",
    },
    {
      id: "32-9",
      name1: "Autres",
      src: "/pictos/autre.svg",
    },
  ];
  let fuites = [
    "En sortie du robinet",
    "À la base du robinet",
    "Au niveau des flexibles",
    "Au niveau du siphon/évacuation",
    "Au niveau des joints silicone",
    "Je ne sais pas",
  ];
  let fuites2 = [
    "Au niveau du robinet",
    "Au niveau du siphon/évacuation",
    "Au niveau des joints silicone",
    "Je ne sais pas",
  ];
  let fuites3 = [
    "Près du robinet d'arrêt",
    "Entre la cuvette et le reservoir",
    "Sur la pipe d'évacuation",
    "Dans la cuvette",
    "Je ne sais pas",
  ];
  let fuites4 = ["Au niveau du mécanisme de chasse", "Je ne sais pas"];
  let fuites5 = ["Au niveau de l'alimentation en eau", "Je ne sais pas"];
  let fuites6 = [
    "Au niveau d'une vanne/robinet",
    "Tuyeau percé, abîmé",
    "Je ne sais pas",
  ];
</script>

<main>
  <div>
    <img src={cpaLogo} class="logo svelte" alt="cycloplomberie Amiens Logo" />
  </div>
  <h1>Formulaire</h1>
  <div class="container">
    {#if count === 1}
      <h2 class="titre-chaudiere">Décrivez votre problème ou votre projet</h2>
      {#each level1 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => {
            etape.push(name1);
            etape = etape;
          }}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
        </div>
      {/each}
    {/if}
    {#if count === 2 && etape[0] === "Dépannage"}
      {#each level21 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => {
            etape.push(name1);
            etape = etape;
          }}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
        </div>
      {/each}
    {/if}
    {#if count === 2 && etape[0] === "Entretien"}
      <h2 class="titre-chaudiere">Chaudière :</h2>
      <br />
      {#each level22 as { id, name1, src, prix }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => {
            etape.push("Chaudière " + name1);
            etape = etape;
          }}
          on:click={() => (goform = true)}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
          <p class="card-tarif">tarif : {prix} €</p>
        </div>
      {/each}
    {/if}

    {#if count === 3 && etape[1] === "Fuite"}
      <h2 class="titre-chaudiere">Le problème concerne :</h2>
      {#each level31 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => {
            etape.push(name1);
            etape = etape;
          }}
          on:click={() => (goform = true)}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
        </div>
      {/each}
    {/if}

    {#if count === 3 && etape[1] === "Canalisation bouchée"}
      <h2 class="titre-chaudiere">Le problème concerne :</h2>
      {#each level32 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => {
            etape.push(name1);
            etape = etape;
          }}
          on:click={() => (goform = true)}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
        </div>
      {/each}
    {/if}

    {#if goform === true || etape[0] === "Pose"}
      <div class="container-form">
        <p class="probleme-resume">
          Vous nous contactez pour : <span class="strong">
            {#each etape as pb}
              <span>{pb.toLowerCase()} </span>
            {/each}
          </span>
        </p>
        <!-- <p class="probleme-resume">
          Vous nous contactez pour : <span class="strong"
            >{etape1.toLowerCase()}
            {#if etape2}
              {etape2.toLowerCase()}
            {/if}
            {#if etape3}
              {etape3.toLowerCase()}
            {/if}
            {#if etape4}
              {etape4.toLowerCase()}
            {/if}
          </span>
        </p> -->
        <div class="fuite-localisation">
          <p>
            Plus précisément où se situe la fuite sur {#if etape[2] === "Lavabo" || etape[2] === "Lave-linge"}
              le
            {:else if etape[2] === "Évier" || etape[2] === "Arrivée d'eau"}l'
            {:else if etape[2] === "WC suspendues" || etape[2] === "Canalisations" || etape[2] === "WC classiques"}les
            {:else}
              la
            {/if}
            {etape[2]} :
          </p>
          <div class="fuite-localisation-list">
            {#if etape[2] === "Lavabo" || etape[2] === "Évier"}
              {#each fuites as fuite}
                <label class="form-control">
                  <input
                    class="checkmark"
                    type="radio"
                    bind:group={etape[3]}
                    name="fuites"
                    value={fuite}
                  />
                  {fuite}
                </label>
              {/each}
            {/if}

            {#if etape[2] === "Baignoire" || etape[2] === "Douche"}
              {#each fuites2 as fuite2}
                <label class="form-control">
                  <input
                    class="checkmark"
                    type="radio"
                    bind:group={etape[3]}
                    name="fuites2"
                    value={fuite2}
                  />
                  {fuite2}
                </label>
              {/each}
            {/if}

            {#if etape[2] === "WC classiques"}
              {#each fuites3 as fuite}
                <label class="form-control">
                  <input
                    class="checkmark"
                    type="radio"
                    bind:group={etape[3]}
                    name="fuites3"
                    value={fuite}
                  />
                  {fuite}
                </label>
              {/each}
            {/if}

            {#if etape[2] === "WC suspendues"}
              {#each fuites4 as fuite}
                <label class="form-control">
                  <input
                    class="checkmark"
                    type="radio"
                    bind:group={etape[3]}
                    name="fuites4"
                    value={fuite}
                  />
                  {fuite}
                </label>
              {/each}
            {/if}

            {#if etape[2] === "Lave-linge"}
              {#each fuites5 as fuite}
                <label class="form-control">
                  <input
                    class="checkmark"
                    type="radio"
                    bind:group={etape[3]}
                    name="fuites5"
                    value={fuite}
                  />
                  {fuite}
                </label>
              {/each}
            {/if}

            {#if etape[2] === "Canalisations" || etape[2] === "Arrivée d'eau"}
              {#each fuites6 as fuite}
                <label class="form-control">
                  <input
                    class="checkmark"
                    type="radio"
                    bind:group={etape[3]}
                    name="fuites6"
                    value={fuite}
                  />
                  {fuite}
                </label>
              {/each}
            {/if}
          </div>
        </div>
        <form action="" class="cpa-form">
          <h2>Renseignements</h2>
          <div class="info">
            <input
              class="fname"
              type="text"
              name="name"
              placeholder="Full name"
            />
            <input type="text" name="name" placeholder="Email" />
            <input type="text" name="name" placeholder="Phone number" />
            <input type="text" name="name" placeholder="Website" />
          </div>
          <p>Message</p>
          <div>
            <textarea rows="4" />
          </div>
          <button type="submit" href="/">Submit</button>
        </form>
      </div>
    {/if}
  </div>
  <div>
    {#if count > 1 || etape[0] === "Pose"}
      <button on:click={() => (goform = false)} on:click={decrement}>
        retour
      </button>
    {/if}

    <!-- {#if count > 1 && etape[0] !== "Pose"}
      <button on:click={() => (goform = false)} on:click={decrement}>
        retour
      </button>
    {/if}

    {#if count > 1 && etape[0] === "Pose"}
      <button on:click={() => ((goform = false), (etape[0] = ""), (count = 1))}>
        retour
      </button>
    {/if} -->
  </div>
  <p>compteur {count}</p>
  <ul>
    <!-- <li>2 {etape2}</li>
    <li>3 {etape3}</li>
    <li>4 {etape4}</li> -->
    {#each etape as pb}
      <li>{pb}</li>
    {/each}

    <li>form {goform}</li>
  </ul>
</main>

<style>
  .logo {
    height: 6em;
    /* padding: 1.5em; */
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 §em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }

  .card-elem {
    width: 100%;
  }

  .card-img {
    height: 50%;
    width: 5rem;
    filter: invert(65%) sepia(60%) saturate(6969%) hue-rotate(350deg)
      brightness(97%) contrast(89%);
  }
</style>
