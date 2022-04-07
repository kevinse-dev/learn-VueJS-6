<template>
  <div id="app">
    <div>
      <pre>
        {{ JSON.stringify(formValues, null, 2) }}
      </pre>
    </div>
    <form @submit="submitForm">
      <div>
        <label for="name">Name : </label>
        <input type="text" id="name" v-model="formValues.name" />
      </div>

      <div>
        <label for="profile">Profile Summery : </label>
        <textarea id="profile" cols="30" rows="10" v-model="formValues.profileSummery"></textarea>
      </div>

      <div>
        <label for="country">Country : </label>
        <select id="country" v-model="formValues.country">
          <option value="">select a country</option>
          <option value="indonesia">Indonesia</option>
          <option value="mexico">Mexico</option>
          <option value="amerika">America</option>
          <option value="palestina">Palestina</option>
          <option value="rusia">Rusia</option>
        </select>
      </div>

      <div>
        <label for="job-location">Job Location : </label>
        <select id="job-location" v-model="formValues.jobLocation" multiple>
          <option value="indonesia">Indonesia</option>
          <option value="mexico">Mexico</option>
          <option value="amerika">America</option>
          <option value="palestina">Palestina</option>
          <option value="rusia">Rusia</option>
        </select>
      </div>

      <div>
        <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no" />
        <label for="remoteWork">Open to Remote Work?</label>
      </div>

      <div>
        <label for="skillSet">Skill Set</label>
        <input type="checkbox" id="html" value="html" v-model="formValues.skillSet" />
        <label for="html">HTML</label>
        
        <input type="checkbox" id="css" value="css" v-model="formValues.skillSet" />
        <label for="css">CSS</label>
        
        <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillSet" />
        <label for="javascript">JAVASCRIPT</label>
      </div>

<div>
  <label for="0-2">0-2</label>
  <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsExperience">
  
  <label for="3-5">3-5</label>
  <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsExperience">
  
  <label for="6-10">6-10</label>
  <input type="radio" id="6-10" value="6-10" v-model="formValues.yearsExperience">
  
</div>

  <idv>
    <button>Submit</button>
  </idv>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      formValues: {
        name: "",
        profileSummery: "",
        country: "",
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        yearsExperience: ''
      },
    };
  },
  methods: {
    submitForm(event){
      event.preventDefault()
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
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
