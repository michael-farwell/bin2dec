<template>
    <div class="hello">
        <b-row>
            <b-col sm="6">
                <b-card title="Binary">
                    <b-form-input v-model="userBinary"
                                  placeholder="Enter a binary number">
                    </b-form-input>
                </b-card>
            </b-col>
            <b-col sm="6">
                <b-card title="Decimal">
                    <b-card-text class="lead">
                        {{userDec}}
                    </b-card-text>
                </b-card>
            </b-col>
        </b-row>
    </div>
</template>

<script>
  export default {
    data() {
      return {
        userBinary: '',
        userDec: null,
      };
    },
    watch: {
      userBinary() {
        if (this.userBinary.match(/^[0-1]+$/g)) {
          return this.userDec = this.convertToDec(this.userBinary);
        } else {
          return this.userDec = 'Please enter a binary number';
        }
      },
    },
    methods: {
      convertToDec: (binary) => {
        const bLength = binary.length;
        let dec = 0;
        binary.split('').forEach((n, i) => {
          dec += (Number(n) * 2 ** (bLength - (i + 1)));
        });
        return dec;
      },
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
