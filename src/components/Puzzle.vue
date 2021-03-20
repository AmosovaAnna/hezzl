<template>
  <div class="puzzle flex">
      <div class="puzzle__piece flex"></div>
      <div :style="{'background-color': piece.backgroundColor}" v-for="piece of pieces" v-bind:key="piece.id" class="puzzle__piece flex pointer">
        <img v-if="piece.img" :src="piece.img" alt="Часть паззла">
        <i v-if="!piece.img" class="fas fa-puzzle-piece"></i>
      </div>
  </div>
</template>

<style scoped lang="scss">
  .puzzle {
    width: 350px;
    height: 350px;
    flex-wrap: wrap;
    overflow: hidden;
    border-radius: 20px;
    background: url(https://storage.theoryandpractice.ru/tnp/uploads/image_unit/000/156/586/image/base_87716f252d.jpg) no-repeat;
    background-size: cover;
    align-content: space-around;
    justify-content: space-around;
    margin-left: 20px;
    @media only screen and (max-width: 992px){
      & {
        display: none;
      }
    }
    &__piece {
      width: 114px;
      height: 114px;
      overflow: hidden;
      align-items: center;
      justify-content: center;
      img {
        object-fit: cover;
      }
      &.pointer:hover {
        filter: brightness(0.8);
      }
      i.fas {
        color: white;
        // text-shadow: 0 0 7px #25232394;
        font-size: 31.1px;
      }
    }
  }
</style>

<script>
export default {
  name: 'Puzzle',
  data: () => {
    return {
      pieces: [
        {
          id: 1,
          img: '',
          backgroundColor: '#E63782'
        },
        {
          id: 2,
          img: '',
          backgroundColor: '#22A4DC'
        },
        {
          id: 3,
          img: '',
          backgroundColor: '#F7AB29'
        },
        {
          id: 4,
          img: '',
          backgroundColor: '#AAC72E'
        },
        {
          id: 5,
          img: '',
          backgroundColor: '#E63782'
        },
        {
          id: 6,
          img: '',
          backgroundColor: '#22A4DC'
        },
        {
          id: 7,
          img: '',
          backgroundColor: '#F7AB29'
        },
        {
          id: 8,
          img: '',
          backgroundColor: '#AAC72E'
        }
      ]
    }
  }
}
</script>
