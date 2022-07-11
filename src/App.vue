<template>
  <form action="" @submit.prevent="submitForm">
    <div>
      <pre>
        {{JSON.stringify(formValues, null, 2)}}
      </pre>
    </div>
    
    <div>
      <label for="name">name</label>
      <input type="text"  id="name" v-model.trim.lazy="formValues.name" >
    </div>

    <div>
      <label for="profile">Profile Summary</label>
      <textarea type="text"  id="profile" v-model="formValues.profileSummary" />
    </div>

    <div>
      <label for="country">country</label>
      <select v-model="formValues.country">
        <option>Select a country</option>
        <option value="Philippines">Philippines</option>
        <option value="Japan">Japan</option>
        <option value="China">China</option>
      </select>
    </div>

    <div>
      <label for="jobLocation">job location</label>
      <select v-model="formValues.jobLocation" multiple>
        <option value="Philippines">Philippines</option>
        <option value="Japan">Japan</option>
        <option value="China">China</option>
      </select>
    </div>

    <div>
      <input type="checkbox" name="" id="remoteWork" v-model="formValues.remoteWork" true-value="yes"  false-value="no" />
      <label for="remoteWork">Open to remote work?</label>
    </div>

      <div>
        <input type="checkbox" name="" id="html" value="html" v-model="formValues.skillSets"/>
        <label for="html">Html</label>

        <input type="checkbox" name="" id="javascript" value="javascript" v-model="formValues.skillSets"/>
        <label for="javascript">javascript</label>

        <input type="checkbox" name="" id="Css" value="Css" v-model="formValues.skillSets"/>
        <label for="Css">Css</label>
      </div>

      <div>
        <input type="radio" name="" id="0-2" value="0-2" v-model="formValues.yearsOfExperience"/>
        <label for="0-2">0-2</label>

        <input type="radio" name="" id="3-5" value="3-5" v-model="formValues.yearsOfExperience"/>
        <label for="3-5">3-5</label>

        <input type="radio" name="" id="6+" value="6+" v-model="formValues.yearsOfExperience"/>
        <label for="6+">6+</label>
      </div>

      <div>
        <input type="number" name="" id="age" @keyup.enter="submitForm" v-model.number="formValues.age"/>
        <label for="age">Age</label>
    </div>

      <button type="submit">submit</button>

  </form>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      formValues: {
        name: '',
        profileSummary: '',
        country: '',
        jobLocation: [],
        remoteWork: 'no',
        skillSets: [],
        yearsOfExperience: '',
        age: null
      }
    }
  },
  methods: {
    displayName () {
      alert(this.name)
    },
    submitForm () {
      console.log('form values', this.formValues)
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}


</style>
