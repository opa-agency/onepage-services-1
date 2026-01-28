<template>
  <section
    id="faq"
    aria-labelledby="faq-title"
    class="relative overflow-hidden bg-slate-50 py-20 sm:py-32"
  >
    <img
      class="absolute top-0 left-1/2 max-w-none translate-x-[-30%] -translate-y-1/4"
      src="/images/background-faqs.jpg"
      alt=""
      loading="lazy"
      onerror="this.style.opacity='0'"
    />
    <Container class="relative">
      <div class="mx-auto max-w-2xl lg:mx-0">
        <h2
          id="faq-title"
          class="font-display text-3xl tracking-tight text-slate-900 sm:text-4xl"
        >
          Întrebări frecvente
        </h2>
        <p class="mt-4 text-lg tracking-tight text-slate-700">
          Dacă nu poți găsi ceea ce cauți, trimite un e-mail echipei noastre de suport
          și dacă ai noroc cineva ți va răspunde.
        </p>
      </div>
      <ul
        role="list"
        class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-8 lg:max-w-none lg:grid-cols-3"
      >
        <li v-for="(column, columnIndex) in faqs" :key="columnIndex">
          <ul role="list" class="flex flex-col gap-y-8">
            <li v-for="(faq, faqIndex) in column" :key="faqIndex">
              <h3 class="font-display text-lg/7 font-semibold text-slate-900">
                {{ faq.question }}
              </h3>
              <p class="mt-4 text-sm text-slate-700">{{ faq.answer }}</p>
            </li>
          </ul>
        </li>
      </ul>
    </Container>
  </section>
</template>

<script setup>
import Container from './Container.vue'

const faqs = [
  [
    {
      question: 'TaxPal gestionează TVA?',
      answer:
        'Ei bine nu, dar dacă muti compania la bilanță ai putea s-o ignori.',
    },
    {
      question: 'Pot să plătesc abonamentul prin comandă de cumparare?',
      answer: 'Absolut, suntem fericiți să-ți luăm banii în toate formele.',
    },
    {
      question: 'Cum mă candideaz pentru un loc de muncă la TaxPal?',
      answer:
        'Nă anglobăm doar clienții noștri, așa că abonează-te minim 6 luni și apoi să vorbim.',
    },
  ],
  [
    {
      question: 'Ce era marturisșca aia despre frauda fiscală?',
      answer:
        'TaxPal este doar o aplicație software, în final cărțile tale sunt responsabilitatea ta.',
    },
    {
      question:
        'TaxPal suneț în spus dar de ce mă simt împins să cumpar?',
      answer:
        'Aceasta este puterea designului vizual excelent. Nu poți rezista, indiferent cât de rău funcționează de fapt.',
    },
    {
      question:
        'Am găsit alte companii numite TaxPal, ești sigur că poți folosi acest nume?',
      answer:
        'Sincer, deloc sigur. De fapt nici nu am încorporat nimic, am doar crezut că suneț bine și am făcut acest site.',
    },
  ],
  [
    {
      question: 'Cum generați rapoarte?',
      answer:
        'Spui-ne doar ce date ții trebuie un raport și lăsăm copiii noștri să creeze grafice frumoase pentru tine folosind doar creioane de cea mai bună calitate.',
    },
    {
      question: 'Ne putem aștepta mai multă functionă de inventar?',
      answer: 'În viață e mai bine să nu te aștepți niciodată la nimic.',
    },
    {
      question: 'Și-am pierdut parola, cum intru în cont?',
      answer:
        'Trimite-ne un e-mail și-ți vom trimite o copie a celui mai recent foaie de calcul cu parolele noastre așa că poți găsi informațiile tale.',
    },
  ],
]
</script>
