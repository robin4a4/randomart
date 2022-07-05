<script lang="ts">
  import illu from "./assets/magic-trick-front-gradient.jpg";
  import Badge from "./components/badge.svelte";

  let randomNumber = Math.random();

  function regenerate() {
    randomNumber = Math.random();
  }

  const typeOfWorks = [
    "un poster",
    "une affiche de metro",
    "une story insta",
    "un dépliant",
    "une infographie",
  ];

  const subjects = [
    "un rubix cube",
    "une ampoule connectée",
    "une bibliothêque",
    "une école d'informatique privé",
    "le salon du vin",
    "un évenement carritatif lié au volleyball",
    "un paquet de mouchoir",
    "des bougies",
    "un microphone",
    "des croquettes",
    "des boucles d'oreilles",
  ];

  let typeOfWork: string;
  let subject: string;
  $: typeOfWork = typeOfWorks[Math.floor(randomNumber * typeOfWorks.length)];
  $: subject = subjects[Math.floor(randomNumber * subjects.length)];
</script>

<main
  class="flex flex-col items-center justify-center h-screen gap-32 px-16 md:gap-72"
>
  <img
    width="100"
    height="100"
    src={illu}
    alt="Magic trick illu"
    class="w-[150px] h-[150px] md:w-[300px] md:h-[300px] bg-gray-50 p-16 md:p-32 rounded-md md:rounded-[32px]"
  />
  <p class="flex flex-col md:block text-32 md:text-64">
    Réaliser <Badge text={typeOfWork} /> sur <Badge text={subject} />
  </p>
  <button
    on:click={regenerate}
    type="button"
    class="px-32 py-16 font-bold tracking-wider text-white duration-100 rounded-md text-18 md:text-32 bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 hover:scale-110"
    >Générer</button
  >
</main>
