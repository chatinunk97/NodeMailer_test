
<a name="readme-top"></a>



<!-- PROJECT LOGO -->
<br />
<div align="center">
    <h3> This is a quick tutorial for NodeMailer </h3>

*   This README template was originally from 
<a href="https://github.com/othneildrew/Best-README-Template/tree/master">
here
</a>
</div>




<!-- ABOUT THE PROJECT -->
## Setup

1. Start by setting up your Express Project

```js
   pnpm init
   pnpm add express dotenv
   ```

2. Then create an index.js file and paste in the following code
```js
const express = require('express')
const app = express()
const port = 3000


app.listen(port, () => {
  console.log(`nodemailerProject is listening at http://localhost:${port}`)
})
```
   
