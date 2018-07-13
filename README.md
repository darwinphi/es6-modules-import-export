# es6-modules-import-export
How to use import and export ES6 modules.

You can export anything that you can assign to a variable. (e.g.  functions, classes, constants etc.).

### 1. Named Export. Export one or multiple variables.

```javascript
// script1.js
const firstName = 'Darwin';
const lastName = 'Manalo';

export { firstName, lastName };
```
```javascript
// script2.js
import { firstName, lastName } from './script1.js';

console.log(firstName); // Darwin
```

### 2. Import all variables as an object using an alias
```javascript
// script2.js
import * as user from './script1.js';

console.log(user.firstName); // Darwin
```

```javascript
// script2.js
import { firstName as name } from './script1.js';

console.log(name) // Darwin
```

### 3. Default Statement
```javascript
// script1.js
const darwin = {
    firstName: 'Darwin',
    lastName: 'Manalo'
};

export default darwin;
```
```javascript
// script2.js
import user from './script1.js';

console.log(user); // { firstName: 'Darwin', lastName: 'Manalo'}
```

### 4.  The import name can differ from the exported default name.
```javascript
// script1.js
const firstName = 'Darwin';
const lastName = 'Manalo';

const user = {
    firstName,
    lastName,
};

export { firstName, lastName };

export default user;
```
```javascript
// script2.js
import user, { firstName, lastName } from './script2.js';

console.log(user); // { firstName: 'Darwin', lastName: 'Manalo' }

console.log(firstName, lastName); // Darwin Manalo
```

### 5. Export the variables directly
```javascript
// script1.js
export const firstName = 'Darwin';
export const lastName = 'Manalo';
```
