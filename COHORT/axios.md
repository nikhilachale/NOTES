
fetch is basically a function in js 

to api it fetches data and to convert in to json need extra async function ()

```
//fetch 
const response =fetch("fwevp/api/jicwepsdvns");
const json =await response.json();
console.log(json); 
```
by default get can be done by mentioning method=post;


axios

```
//axios
const response =await axios.get("fwevp/api/jicwepsdvns");
console.log(response.data);
```
axios.post