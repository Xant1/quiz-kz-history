<script setup>
import { ref, computed } from 'vue';

const questions = ref([
  {
    question: 'Қазақ хандығы құрылған жыл?',
    answer: 0,
    options: ['1465 жыл', '1455 жыл', '1445 жыл'],
    selected: null,
  },
  {
    question:
      'Грек-Македон басқыншыларына қарсы күресті басқарған сақ жауынгері?',
    answer: 2,
    options: ['Мөде', 'Томирис', 'Спитамен'],
    selected: null,
  },
  {
    question: 'Семей полигонындағы алғашқы ядролық сынақ болған жыл?',
    answer: 1,
    options: ['1959 жылы', '1949 жылы', '1945 жылы'],
    selected: null,
  },
  {
    question:
      '1993ж. Президент Н.Ә. Назарбаев қол қойған Лиссабон протоколы бойынша Қазақстан:?',
    answer: 0,
    options: [
      'Ядролық қарудан босаған ел',
      'Демократиялық мемлекет',
      'Еркін экономикалық аймақ',
    ],
    selected: null,
  },
  {
    question: 'Қазақстан жеріндегі сақ тайпалары туралы жазған?',
    answer: 2,
    options: ['Үнділер', 'Қытайлар', 'Парсылар'],
    selected: null,
  },
  {
    question: 'Ең көне тас құралдар қай жерден табылды?',
    answer: 0,
    options: ['Оңтүстік Қазақстан', 'Орталық Қазақстан', 'Батыс Қазақстан'],
    selected: null,
  },
  {
    question: '1986 ж. желтоқсанда қазақ жастарының бой көтеруі:?',
    answer: 2,
    options: [
      'Ұлтшылдық сипатта болды',
      'Құқыққа қарсы сипатта болды',
      'Бейбіт және саяси сипатта болды',
    ],
    selected: null,
  },
  {
    question: 'Сақтардың негізгі шаруашылығы?',
    answer: 2,
    options: ['Егіншілік', 'Қол өнері', 'Мал шаруашылығы'],
    selected: null,
  },
  {
    question: 'Сақтар туралы мәлімет беретін жазба мәтіндері сақталған елдер?',
    answer: 0,
    options: [
      'Грек, Парсы авторларының шығармалары',
      'Қытай, Парсы',
      'Рим, Парсы, Үнді',
    ],
    selected: null,
  },
  {
    question: 'Сақ патшайымы Томиристің өмір сүрген мерзімі?',
    answer: 1,
    options: ['б.з.б. 520-450 жж', 'б.з.б. 570-520 жж', 'б.з.б. 550-505 жж'],
    selected: null,
  },
  {
    question: 'Үйсіндер басшысының атауы?',
    answer: 0,
    options: ['Гуньмо', 'Патша', 'Хан'],
    selected: null,
  },
  {
    question: 'Қазақ хандығының құрылуы қай сұлтандар есімімен байланысты?',
    answer: 2,
    options: ['Қасым мен Хақназар', 'Абылай мен Уәли', 'Жәнібек пен Керей'],
    selected: null,
  },
  {
    question: 'Жоңғарларға қарсы күресте қол бастаған қазақ батыры:?',
    answer: 1,
    options: ['Сырым', 'Бөгенбай', 'Исатай'],
    selected: null,
  },
  {
    question: 'Қазақстанда 1965 жылы өзінің алғашқы мұнайын берген:?',
    answer: 2,
    options: ['Мұнайлы', 'Қарашығанақ', 'Өзен'],
    selected: null,
  },
  {
    question: 'Қазақстан Республикасы Туының авторы?',
    answer: 0,
    options: ['Ш.Ниязбеков', 'Х.Наурызбаев', 'Ж.Мәлібеков'],
    selected: null,
  },
  {
    question:
      'Жамбыл обылысындағы 5 мыңға жуық тас құралдар табылған тұрақтар?',
    answer: 1,
    options: ['Атасу, Пеньки', 'Бөріқазған, Шабақты', 'Тесіктас, Семізбұғы'],
    selected: null,
  },
  {
    question: 'Орал облысында Кеңес үкіметі қашан түпкілікті орнады??',
    answer: 1,
    options: [
      'Петроградтағы Қазан төңкерілісінен кейінгі екінші күні',
      'Азамат соғысы кезінде',
      'Кеңес үкіметінің салтанатты шеруі кезінде',
    ],
    selected: null,
  },
  {
    question: '«Сібір қазақтарының Ереже» бойынша аға сұлтанды сайлаушылар:?',
    answer: 0,
    options: ['Тек сұлтандар', 'Батырлар', 'Билер'],
    selected: null,
  },
  {
    question: 'Қаңлы мемлекетінің оңтүстігіндегі көршісі?',
    answer: 1,
    options: ['Алан', 'Үйсін', 'Парсы'],
    selected: null,
  },
  {
    question: '1991 жылы желтоқсанның бірінде:?',
    answer: 2,
    options: [
      'Қазақстан компартиясы таратылды',
      'ҚКСРсын Қазақстан Республикасы деп атау жөнінде шешім қабылданды',
      'Н.Ә.Назарбаев Қазақстан Президенті болып сайланды',
    ],
    selected: null,
  },
  {
    question:
      'Орталық Қазақстан жеріндегі кейінгі полеолитке жататын 300-ге таяу тас қүрал шыққан ең көрнекті көне мекен?',
    answer: 2,
    options: ['Атасу', 'Шабақты', 'Батпақ'],
    selected: null,
  },
  {
    question: 'Қазақстанда жергілікті кеңестер өзін-өзі тарата бастады?',
    answer: 0,
    options: [
      '1993 жылдың күзінде',
      '1991 жылдың жазында',
      '1992 жылдың қысында',
    ],
    selected: null,
  },
  {
    question: 'XVІІІ ғ. қазақ жерлерін қалпына келтіріп, билік жүргізген:?',
    answer: 1,
    options: ['Әбілмәмбет', 'Абылай', 'Әбілқайыр'],
    selected: null,
  },
  {
    question:
      'Тас дәуірінің ескерткіші - Бөріқазған Қазақстанның қай өңірінен табылды?',
    answer: 2,
    options: [
      'Батыс Қазақстаннан',
      'Оңтүстік Қазақстаннан',
      'Солтүстік Қазақстаннан',
    ],
    selected: null,
  },
  {
    question: 'Алтын Орданың негізін қалаған хан?',
    answer: 0,
    options: ['Батый', 'Берке', 'Өзбек'],
    selected: null,
  },
]);

const quizCompleted = ref(false);
const currentQuestion = ref(0);
const score = computed(() => {
  let value = 0;
  questions.value.map((q) => {
    if (q.selected != null && q.answer == q.selected) {
      console.log('correct');
      value++;
    }
  });
  return value;
});

const getCurrentQuestion = computed(() => {
  let question = questions.value[currentQuestion.value];
  question.index = currentQuestion.value;
  return question;
});

const SetAnswer = (e) => {
  questions.value[currentQuestion.value].selected = e.target.value;
  e.target.value = null;
};

const NextQuestion = () => {
  if (currentQuestion.value < questions.value.length - 1) {
    currentQuestion.value++;
    return;
  }

  quizCompleted.value = true;
};
</script>

<template>
  <main class="app">
    <h1>Қазақстан Тарихы</h1>

    <section class="quiz" v-if="!quizCompleted">
      <div class="quiz-info">
        <span class="question">{{ getCurrentQuestion.question }}</span>
        <span class="score">Ұпай {{ score }}/{{ questions.length }}</span>
      </div>

      <div class="options">
        <label
          v-for="(option, index) in getCurrentQuestion.options"
          :for="'option' + index"
          :key="index"
          :class="`option ${
            getCurrentQuestion.selected == index
              ? index == getCurrentQuestion.answer
                ? 'correct'
                : 'wrong'
              : ''
          } ${
            getCurrentQuestion.selected != null &&
            index != getCurrentQuestion.selected
              ? 'disabled'
              : ''
          }`"
        >
          <input
            type="radio"
            :id="'option' + index"
            :name="getCurrentQuestion.index"
            :value="index"
            v-model="getCurrentQuestion.selected"
            :disabled="getCurrentQuestion.selected"
            @change="SetAnswer"
          />
          <span>{{ option }}</span>
        </label>
      </div>

      <button @click="NextQuestion" :disabled="!getCurrentQuestion.selected">
        {{
          getCurrentQuestion.index == questions.length - 1
            ? 'Соңы'
            : getCurrentQuestion.selected == null
            ? 'Таңдаңыз'
            : 'Келесі'
        }}
      </button>
    </section>

    <section v-else>
      <h2>Сіз квизді аяқтадыңыз!</h2>
      <p>Сіздің ұпайыңыз: {{ score }}/{{ questions.length }}</p>
    </section>
  </main>
</template>

<style></style>
