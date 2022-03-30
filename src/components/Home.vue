<template>
    <h1>Laundry</h1>
    <div>
      <label for="velg-program">Velg program</label>
      <select v-model="fieldOne" name="velg-program" id="velg-program">
        <option disabled value="">Velg program</option>
        <option  value=1 >Kokevask</option>
        <option  value=1 >Tøyvask</option>
        <option  value=1 >Håndvask</option>
      </select>
    </div>
    <div>
      <label for="velg-dato">Velg dato</label>
      <input v-model="fieldTwo"
        type="date" id="velg-dato" name="velg-dato"
        min="2018-01-01" max="2018-12-31">
    </div>
    <div>
      <label for="velg-tid">Velg klokkeslett</label>
      <input disabled="disabled"
        type="time" id="velg-tid" name="velg-tid"
        min="09:00" max="18:00" required>
    </div>
    <div @click="toggleMenu" class="book-button">
        <span v-if="!showMenu"><h3>Reserver</h3></span>
        <span v-else><h3>Avlys</h3></span>
    </div>
    <div>
        <span v-if="!showMenu"><img src="../assets/logo-crest.svg" alt="reserved" class="nav-icon"></span>
        <span v-else><img src="../assets/logo-lion-beige.svg" alt="available" class="nav-icon"></span>
    </div>
</template>

<script>
export default {
    data() {
        return{
            showMenu: false,
            activate: false,
            disable: true,
            fieldTwo: false,
            fieldThree: false,
            fieldOne: 0,

        }
    },
    methods: {
        toggleMenu() {
            this.showMenu = !this.showMenu
        },
        activate() {
          if(this.fieldOne.value >= 0) {
            this.fieldTwo = true
          }
          if(this.fieldTwo.value >= 1) {
            this.fieldThree = true
          }
        }
    },
}
</script>

<style lang="scss">
  .book-button {
    height: 50px;
    width: 300px;
    color: black;
    background-color: lightgray;
  }

</style>