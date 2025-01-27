# vivo-test-key

## Converting PEM to JWKS format

To convert a PEM key to JWKS format, you can use the following example. This example uses the `jwtRS256.key.pub` file.

1. Install the `pem-jwk` package:
   ```sh
   npm install pem-jwk
   ```

2. Create a JavaScript file (e.g., `convert.js`) with the following content:
   ```js
   const fs = require('fs');
   const pemJwk = require('pem-jwk');

   const pem = fs.readFileSync('jwtRS256.key.pub');
   const jwk = pemJwk.pem2jwk(pem);

   console.log(JSON.stringify({ keys: [jwk] }, null, 2));
   ```

3. Run the JavaScript file to generate the JWKS format:
   ```sh
   node convert.js > jwtRS256.key.pub.jwks
   ```

This will create a new file `jwtRS256.key.pub.jwks` containing the JWKS format of the PEM key.
