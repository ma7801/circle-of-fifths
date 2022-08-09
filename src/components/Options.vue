<template>
  <div id="options">
    <div id="col1">
        <h3>Fingering</h3>
        <input type="checkbox" name="fingeringLH"/><label>Left-hand</label>
        <input type="checkbox" name="fingeringRH"/><label>Right-hand</label>
        <h3>Order</h3>
        <input type="radio" name="order" value="fifths" checked="checked"/><label>Fifths</label>
        <input type="radio" name="order" value="fourths"/><label>Fourths</label>
        <input type="radio" name="order" value="chromatic"/><label>Chromatic</label>
    </div>
    <div id="col2">
        <h3>Scales</h3>
        <div>
            <label><strong>Scale #1: </strong></label>
            <select name="scale1" @change="scaleChange">
              <option  v-for="(scale, identifier) in scales" :key="scale" :value="identifier" :selected="identifier === 'major' ? true : false">{{ scale }}</option>
            </select>
        </div>
        <div>
            <label><strong>Scale #2: </strong></label>
            <select name="scale2" @change="scaleChange">
            <option  v-for="(scale, identifier) in scales" :key="scale" :value="identifier">{{ scale }}</option>
            </select>
        </div>
        <div>
            <label><strong>Scale #3: </strong></label>
            <select name="scale3" @change="scaleChange">
            <option  v-for="(scale, identifier) in scales" :key="scale" :value="identifier">{{ scale }}</option>
            </select>
        </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
        scales: {
            "none": "None",
            "major": "Major/Ionian",
            "natMinor": "Natural Minor/Aeolian",
            "harMinor": "Harmonic Minor",
            "melMinor": "Melodic Minor",
            "pentMajor": "Major Pentatonic",
            "pentMinor": "Minor Pentatonic",
            "bluesMajor": "Major Blues",
            "bluesMinor": "Minor Blues",
            "wholeTone": "Whole Tone",
            "lydian": "Lydian",
            "mixolydian": "Mixolydian",
            "dorian": "Dorian",
            "phrygian": "Phrgian",
            "locrian": "Locrian"
        },
    }
  },
  methods: {
    scaleChange(e) {
        this.$emit('scaleChange', e.target.name, e.target.value);
    }
  },
  mounted() {


  }


}
</script>

<style scoped>

</style>