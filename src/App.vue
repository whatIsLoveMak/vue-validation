<template>
  <div id="app">
    <div class="container">
      <div class="modal-content">
        <div class="modal-title">Регистрация</div>
        <div class="modal-already">
          Уже есть аккаунт? <a href="#"> Войти</a>
        </div>
        <form id="modalForm" action="get"></form>
        <t-input
          @get-type="defineInput"
          v-for="item in inputs"
          v-model="item.value"
          :check="check"
          :key="item.type"
          :item="item"
        /> <!-- TODO 3 отдельных инпута ну и сам уже понял погугли как во вью можно сделать валидацию, в офф дока всё неплохо написано
        cделай так чтобы в инпут с телефоном невводились буквы-->
        <label for="">Язык</label> <!-- TODO Задизейбли селект, т.к. язык на самом деле 1 либо кастомизируй дропдаун-->
        <t-select />
        <t-checkbox />
        <button>Зарегистрироваться</button> <!-- TODO Отдельная компонент 2 состояния-->
      </div>
    </div>
  </div>
</template>

<script>
// когда сделаешь валидацию и закончишь с вёрсткой сделай компоент с модалкой, и вызови этот компонент через функцию
// во вью есть функции вызова компонентов, почитай подроблее на хабре или в офф доке
// TODO хочу чтобы ты её заюзал и разобрался с ней, там ничего сложного
import TInput from "@/components/UI/tInput";
import TSelect from "@/components/UI/tSelect";
import TCheckbox from "@/components/UI/tCheckbox";
export default {
  name: "App",
  components: { TCheckbox, TSelect, TInput },
  data() {
    return {
      inputs: [
        {
          value: "",
          type: "text",
          placeholder: "Введите Ваше имя",
          labelInner: "Имя",
          id: "modalForm",
          className: "input",
          error: "wrong name",
        },
        {
          value: "",
          type: "email",
          placeholder: "Введите Ваше email",
          labelInner: "Email",
          id: "modalForm",
          className: "input",
          error: "wrong email",
        },
        {
          value: "",
          type: "tel",
          placeholder: "Введите номер телефона",
          labelInner: "Номер телефона",
          id: "modalForm",
          className: "input",
          error: "wrong number",
        },
      ],
      check: false,
    };
  },
  methods: {
    defineInput(data) {
      if (data.type === "text") {
        console.log(data);
      }
      if (data.type === "email") {
        console.log(data.id);
      }
      if (data.type === "tel") {
        let regular = data.value.replace(/[^0-9.]/g);
        if (regular === data.value) {
          console.log("yes");
        } else {
          this.check = true;
        }
      }
    },
  },
};
</script>
<style>
#app {
  font-size: 16px;
  line-height: 20px;
  color: #756f86;
}
.container {
  max-width: 1000px;
  margin: 0px auto;
  padding: 300px 15px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.modal-content {
  max-width: 460px;
  margin: 0 auto;
  padding: 40px 30px;
  display: flex;
  flex-direction: column;
  width: 100%;
  border-radius: 24px;
  box-shadow: 0px 0px 10px black;
}
.modal-title {
  font-size: 34px;
  line-height: 44px;
  font-weight: 700;
  margin-bottom: 8px;
  color: black;
}
.modal-already {
  margin-bottom: 58px;
  color: black;
}
.modal-already a {
  color: #0880ae;
  text-decoration: none;
}
button {
  width: 100%;
  padding: 18px 0px;
  background: #0880ae;
  border-radius: 6px;
  border: none;
  color: white;
}
</style>
