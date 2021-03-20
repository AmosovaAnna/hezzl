<template>
  <div class="puzzleSettings flex">
      <form class="form" action="#" method="GET">
        <select name="game" disabled class="form__select pointer">
            <option value="puzzle1" selected>Пазл</option>
            <option value="puzzle2">Пазл 2</option>
        </select>
        <div class="form__group flex">
            <label class="form__label">Название</label>
            <div class="form__group flex">
              <label class="form__label flex" for="name_ru">Ru</label>
              <input placeholder="Имя" class="form__input" type="text" name="name_ru" id="name_ru">
            </div>
            <div class="form__group flex">
              <label class="form__label flex" for="name_en">En</label>
              <input placeholder="Name" class="form__input" type="text" name="name_en" id="name_en">
            </div>
        </div>
        <div class="form__group flex">
            <label class="form__label">Картинка пазла</label>
            <label class="form__label label-images pointer flex" for="images-puzzle">
              <svg version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="17" height="17" viewBox="0 0 17 17">
              <path d="M1 1v15h15v-15h-15zM15 15h-13v-2h13v2zM2 12v-10h13v10h-13zM14.203 10.165l-0.697 0.717-2.417-2.349-1.554 1.676-2.486-4.415-3.401 4.975-0.826-0.564 4.31-6.303 2.604 4.622 1.317-1.422 3.15 3.063z" fill="#FFFFFF" />
              </svg>
            </label>
            <div class="form__images-group">
              <label class="form__label label-btn pointer flex" for="images-puzzle">Загрузить</label>
              <input hidden type="file" class="form__input" name="images-puzzle" id="images-puzzle">
              <div class="form__group">
                  Или <a href="#">Выбрать из коллекции</a><br>
                  Разрешение 550*550
              </div>
            </div>
        </div>
        <div class="form__group flex">
          <label class="form__label">Сколько деталей у пазла</label>
          <div class="form__group flex">
            <div class="flex form__count-pieces">
              <label class="form__label" for="horizontal-count">по Горизонтали</label>
              <input disabled name="horizontal-count" id="horizontal-count" value="3" class="form__input" type="number">
            </div>
            <div class="flex form__count-pieces">
              <label class="form__label" for="vertical-count">по Вертикали</label>
              <input disabled id="vertical-count" value="3" class="form__input" name="vertical-count" type="number">
            </div>
          </div>
        </div>
        <div class="form__group flex">
          <label class="form__label flex" for="coupons">Может ли награда<br> выдавать купоны</label>
          <select name="coupons" id="coupons" class="form__select pointer">
              <option value="yes" selected>Да</option>
              <option value="no" >Нет</option>
          </select>
        </div>
        <div class="form__group flex">
            <label class="form__label flex" for="reward-text">Сообщение при<br> получении награды</label>
            <input class="form__input" placeholder="Введите значение" id="reward-text" name="reward-text" type="text">
        </div>
        <div class="form__group flex">
            <label class="form__label flex" for="reward-count">Сколько раз может получить один игрок награду</label>
            <input disabled class="form__input" placeholder="1" value="1" id="reward-count" name="reward-count" type="text"><label class="form__label flex" for="reward-count">Раз</label>
        </div>
      </form>
  </div>
</template>

<style scoped lang="scss">
  .puzzleSettings {
    flex: 1;
    padding: 0 20px;
  }
  .form {
    flex: 1;
    * {
      font-family: 'Roboto', sans-serif;
      font-size: 14px;
    }
    &__group {
      flex-wrap: wrap;
      width: 100%;
    }
    &__images-group {
      padding-left: 20px;
      color: #888EA7;
      a {
        color: #22A4DC;
      }
    }
    &__select {
      border: 2px solid #E6ECF5;
      border-radius: 5px;
      padding: 10px;
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      background: url(../assets/arrow-down.svg) no-repeat;
      width: 100%;
      background-position: calc(100% - 10px) center;
      background-size: 13px;
      margin-bottom: 10px;
      &[disabled] {
        background-color: #E6ECF5;
        &.pointer {
          cursor: not-allowed;
        }
      }
      &[id*="coupons"] {
        flex: 1;
      }
    }
    &__label {
      margin-bottom: 10px;
      width: 100%;
      color: #313643;
      &[for*="name_"] {
        align-items: center;
        justify-content: center;
        margin: 0;
        width: 38px;
        background: #E6ECF5;
        color: #313643;
        margin-bottom: 10px;
        border-radius: 5px 0 0 5px;
      }
      &[for*="coupons"],
      &[for*="reward-text"] {
        width: 150px;
        align-items: center;
        padding-right: 10px;
        @media only screen and (max-width: 480px){
          & {
            width: 100%;
            padding-right: 0;
            br {
              display: none;
            }
          }
        }
      }
      &.label-images {
        width: 100px;
        height: 100px;
        background: #E6ECF5;
        border: 2px solid #E6ECF5;
        border-radius: 5px;
        justify-content: center;
        align-items: center;
        svg {
          box-shadow: 4px 3px 0px -1px #e6ecf5, 4px 3px 0 0 white;
          width: 19px;
          height: 19px;
        }
        &:hover {
          svg {
            box-shadow: none;
            width: 21px;
            height: 21px;
          }
        }
      }
      &.label-btn {
        border: 2px solid #E6ECF5;
        border-radius: 5px;
        padding: 10px 30px;
        width: max-content;
        height: max-content;
        color: #313643;
        &:hover {
          background: #E6ECF5;
          box-shadow: inset 0px 0px 0 2px white;
        }
      }
    }
    &__input {
      padding: 10px;
      flex: 1;
      margin-bottom: 10px;
      border-radius: 5px;
      border: 2px solid #E6ECF5;
      &[disabled] {
        background-color: #E6ECF5;
        cursor: not-allowed;
      }
      &[id*="name_"] {
        border-radius: 0 5px 5px 0;
      }
      &[id*="reward-count"] {
        border-radius: 5px 0 0 5px;
        & + .form__label[for*="reward-count"] {
          width: 43px;
          padding: 10px;
          margin: 0;
          align-items: center;
          height: max-content;
          background: #E6ECF5;
          border: 2px solid #E6ECF5;
          color: #313643;
          border-radius: 0 5px 5px 0;
        }
      }
    }
    &__count-pieces {
      flex: 1;
      justify-content: center;
      align-items: center;
      &:first-child .form__label {
        border-radius: 5px 0 0 5px;
      }
      &:last-child .form__input {
        border-radius: 0 5px 5px 0;
      }
      .form__input {
        flex: 1;
        border-radius: 0;
      }
      .form__label {
        width: 130px;
        padding: 10px;
        background-color: #E6ECF5;
        border: 2px solid #E6ECF5;
      }
    }
  }
</style>

<script>
export default {
  name: 'PuzzleSettings'
}
</script>
