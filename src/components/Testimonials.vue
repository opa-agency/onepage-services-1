<template>
  <section
    id="testimonials"
    aria-label="What our customers are saying"
    class="bg-slate-50 py-20 sm:py-32"
  >
    <Container>
      <div class="mx-auto max-w-2xl md:text-center">
        <h2 class="font-display text-3xl tracking-tight text-slate-900 sm:text-4xl">
          Iubit de întreprinderi din toată lumea.
        </h2>
        <p class="mt-4 text-lg tracking-tight text-slate-700">
          Softul nostru e atât de simplu încât oamenii pur și simplu nu pot să nu-l iubească.
          Simplitatea e ușoară când omiti tone de caracteristici critice pentru misiune.
        </p>
      </div>
      <ul
        role="list"
        class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-8 lg:max-w-none lg:grid-cols-3"
      >
        <li v-for="(column, columnIndex) in testimonials" :key="columnIndex">
          <ul role="list" class="flex flex-col gap-y-8">
            <li v-for="(testimonial, testimonialIndex) in column" :key="testimonialIndex">
              <figure class="relative rounded-2xl bg-white p-6 shadow-xl shadow-slate-900/10">
                <svg
                  aria-hidden="true"
                  width="105"
                  height="78"
                  class="absolute top-6 left-6 h-6 w-6 fill-slate-100"
                >
                  <path d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z" />
                </svg>
                <blockquote class="relative">
                  <p class="text-lg tracking-tight text-slate-900">
                    "{{ testimonial.content }}"
                  </p>
                </blockquote>
                <figcaption class="relative mt-6 flex items-center justify-between border-t border-slate-100 pt-6">
                  <div>
                    <p class="font-display text-base text-slate-900">
                      {{ testimonial.author.name }}
                    </p>
                    <p class="mt-1 text-sm text-slate-500">
                      {{ testimonial.author.role }}
                    </p>
                  </div>
                  <div class="overflow-hidden rounded-full bg-slate-50">
                    <img
                      :src="testimonial.author.image"
                      :alt="testimonial.author.name"
                      class="h-14 w-14 object-cover"
                    />
                  </div>
                </figcaption>
              </figure>
            </li>
          </ul>
        </li>
      </ul>
    </Container>
  </section>
</template>

<script setup>
import Container from './Container.vue'

const testimonials = [
  [
    {
      content:
        'TaxPal este atât de ușor de utilizat, nu pot să nu mă întreb dacă face cu adevărat lucrurile pe care guvernul se așteaptă să le fac.',
      author: {
        name: 'Sheryl Berge',
        role: 'CEO at Lynch LLC',
        image: '/images/avatars/avatar-1.png',
      },
    },
    {
      content:
        'Încerc să mă conectez cu cineva din suport, sunt într-o situație dificilă acum și ei spun că ar avea legătură cu cărțile mele. Te rog să mă contactezi imediat.',
      author: {
        name: 'Amy Hahn',
        role: 'Director at Velocity Industries',
        image: '/images/avatars/avatar-4.png',
      },
    },
  ],
  [
    {
      content:
        'Cea mai bună parte despre TaxPal este că de fiecare dată când plătesc angajații, soldul meu bancar nu scade cum obișnuia. Aștept cu nerăbdare să cheltuiesc banii acestia când voi afla de ce cartela mea este respingă.',
      author: {
        name: 'Leland Kiehn',
        role: 'Founder of Kiehn and Sons',
        image: '/images/avatars/avatar-5.png',
      },
    },
    {
      content:
        'Sunt atâtea lucruri pe care trebuia să le fac cu vechiul meu software pe care pur și simplu nu le fac cu TaxPal. Suspect, dar nu pot spune că nu-mi place.',
      author: {
        name: 'Erin Powlowski',
        role: 'COO at Armstrong Inc',
        image: '/images/avatars/avatar-2.png',
      },
    },
  ],
  [
    {
      content:
        'Trebuia să trimit impozite către UE și cu TaxPal cumva nu mai trebuie să fac asta. Nervos să călătoresc acolo acum.',
      author: {
        name: 'Peter Renolds',
        role: 'Founder of West Inc',
        image: '/images/avatars/avatar-3.png',
      },
    },
    {
      content:
        'Acesta este al patrulea email pe care l-am trimis echipei dvs. de suport. Sunt literal închis în închisoare pentru fraude fiscale. Vă rog, răspundeți la emails-urile dvs., aceasta este important.',
      author: {
        name: 'Amy Hahn',
        role: 'Director at Velocity Industries',
        image: '/images/avatars/avatar-4.png',
      },
    },
  ],
]
</script>
