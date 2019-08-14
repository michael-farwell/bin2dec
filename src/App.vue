<template>
    <div id="app">
        <b-container>
            <b-jumbotron header="Binary to Decimal"
                         lead="Convert a binary number to its decimal counterpart">
                <BinToDec/>
            </b-jumbotron>
        </b-container>
    </div>
</template>

<script>
  import BinToDec from './components/BinToDec.vue';

  export default {
    name: 'app',
    components: {
      BinToDec,
    },
  };
</script>

<style>
</style>
