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
  };

  let etape1;
  let etape2;
  let etape3;
  let etape4;
  let etape5;
  let etape6;
  let goform = false;
  let level1 = [
    { id: "1-1", name1: "Dépannage", src: "/src/assets/pictos/depannage.svg" },
    { id: "1-2", name1: "Pose", src: "/src/assets/pictos/pose.svg" },
    { id: "1-3", name1: "Entretien", src: "/src/assets/pictos/entretien.svg" },
  ];
  let level21 = [
    { id: "21-1", name1: "Fuite", src: "/src/assets/pictos/fuite.svg" },
    {
      id: "21-2",
      name1: "Canalisation bouchée",
      src: "/src/assets/pictos/canalisation-bouchee.svg",
    },
  ];
  let level22 = [
    {
      id: "22-1",
      name1: "Au sol",
      src: "/src/assets/pictos/chaudiere-sol.svg",
      prix: "90",
    },
    {
      id: "22-2",
      name1: "Murale",
      src: "/src/assets/pictos/chaudiere-murale.svg",
      prix: "70",
    },
  ];
  let level31 = [
    { id: "31-1", name1: "Évier", src: "/src/assets/pictos/evier.svg" },
    {
      id: "31-2",
      name1: "Lavabo",
      src: "/src/assets/pictos/lavabo.svg",
    },
    {
      id: "31-3",
      name1: "Baignoire",
      src: "/src/assets/pictos/baignoire.svg",
    },
    {
      id: "31-4",
      name1: "Douche",
      src: "/src/assets/pictos/douche.svg",
    },
    {
      id: "31-5",
      name1: "WC classiques",
      src: "/src/assets/pictos/wc.svg",
    },
    {
      id: "31-6",
      name1: "WC suspendues",
      src: "/src/assets/pictos/wc-suspendus.svg",
    },
    {
      id: "31-7",
      name1: "Lave-linge",
      src: "/src/assets/pictos/lave-linge.svg",
    },
    {
      id: "31-8",
      name1: "Lave-vaisselle",
      src: "/src/assets/pictos/lave-vaisselle.svg",
    },
    {
      id: "31-9",
      name1: "Autres",
      src: "/src/assets/pictos/autre.svg",
    },
  ];
  let level32 = [
    {
      id: "32-10",
      name1: "Canalisation",
      src: "/src/assets/pictos/canalisation.svg",
    },
    {
      id: "32-11",
      name1: "Arrivée d'eau",
      src: "/src/assets/pictos/arrivee-eau.svg",
    },
    { id: "32-1", name1: "Évier", src: "/src/assets/pictos/evier.svg" },
    {
      id: "32-2",
      name1: "Lavabo",
      src: "/src/assets/pictos/lavabo.svg",
    },
    {
      id: "32-3",
      name1: "Baignoire",
      src: "/src/assets/pictos/baignoire.svg",
    },
    {
      id: "32-4",
      name1: "Douche",
      src: "/src/assets/pictos/douche.svg",
    },
    {
      id: "32-5",
      name1: "WC classiques",
      src: "/src/assets/pictos/wc.svg",
    },
    {
      id: "32-6",
      name1: "WC suspendues",
      src: "/src/assets/pictos/wc-suspendus.svg",
    },
    {
      id: "32-7",
      name1: "Lave-linge",
      src: "/src/assets/pictos/lave-linge.svg",
    },
    {
      id: "32-8",
      name1: "Lave-vaisselle",
      src: "/src/assets/pictos/lave-vaisselle.svg",
    },
    {
      id: "32-9",
      name1: "Autres",
      src: "/src/assets/pictos/autre.svg",
    },
  ];
</script>

<main>
  <div>
    <img src={cpaLogo} class="logo svelte" alt="cycloplomberie Amiens Logo" />
  </div>
  <h1>Formulaire</h1>
  <form class="container">
    {#if count === 1}
      {#each level1 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => (etape1 = name1)}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
        </div>
      {/each}
    {/if}
    {#if count === 2 && etape1 === "Dépannage"}
      {#each level21 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => (etape2 = name1)}
          on:click={increment}
          value={name1}
          class="card"
        >
          <img class="card-elem card-img" {src} alt={name1} />

          <h3 class="card-elem">{name1}</h3>
        </div>
      {/each}
    {/if}
    {#if count === 2 && etape1 === "Entretien"}
      <h2 class="titre-chaudiere">Chaudière :</h2>
      <br />
      {#each level22 as { id, name1, src, prix }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => (etape2 = "Chaudière " + name1)}
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

    {#if count === 3 && etape2 === "Fuite"}
      <h2 class="titre-chaudiere">Le problème concerne :</h2>
      {#each level31 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => (etape3 = name1)}
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

    {#if count === 3 && etape2 === "Canalisation bouchée"}
      {#each level32 as { id, name1, src }}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
          on:click={() => (etape3 = name1)}
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

    {#if goform === true || etape1 === "Pose"}
      <h1>Contact Us</h1>
      <div class="info">
        <input class="fname" type="text" name="name" placeholder="Full name" />
        <input type="text" name="name" placeholder="Email" />
        <input type="text" name="name" placeholder="Phone number" />
        <input type="text" name="name" placeholder="Website" />
      </div>
      <p>Message</p>
      <div>
        <textarea rows="4" />
      </div>
      <button type="submit" href="/">Submit</button>
    {/if}
  </form>
  <div>
    {#if count > 1 && etape1 !== "Pose"}
      <button on:click={() => (goform = false)} on:click={decrement}>
        retour
      </button>
    {/if}

    {#if count > 1 && etape1 === "Pose"}
      <button on:click={() => ((goform = false), (etape1 = ""), (count = 1))}>
        retour
      </button>
    {/if}
  </div>
  <p>étape {count}</p>
  <ul>
    <li>{etape1}</li>
    <li>{etape2}</li>
    <li>{etape3}</li>
    <li>{etape4}</li>
    <li>{goform}</li>
  </ul>

  <p class="read-the-docs">Click on the Vite and Svelte logos to learn more</p>
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
  .read-the-docs {
    color: #888;
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
