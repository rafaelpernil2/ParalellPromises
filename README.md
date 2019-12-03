# ParalellPromises

In this project I explore the concept of paralell promises and implement a method for executing a list of promises with a determined concurency limit.
This project is inspired by https://itnext.io/node-js-handling-asynchronous-operations-in-parallel-69679dfae3fc

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [Credits](#credits)
- [License](#license)

## Installation

Install it on your project
```Shell
npm install --save paralell-promises
```

## Usage
**Usage with Typescript**

```typescript
import { customPromiseAll } from 'paralell-promises';

...

const concurrentLimit: number = 5;

const listOfPromises: ICustomPromise[] = [
      {
        name: 'GetSomething',
        function: this.operationWrapper.getSomethingFunction,
        thisArg: this.operationWrapper,
        args: ["firstParamForFunction",{ data: "Another param"}, ["more params..."]]
      },
      {
        name: 'CreateSomething',
        function: this.createSomething,
        thisArg: undefined,
        args: ["firstParamForFunction"]
      },
      {
        name: 'RefreshSomething',
        function: this.updateSomething,
      },
      ... 
      ]

      customPromiseAll(listOfPromises, concurrentLimit).then((result)=>{
          console.log(result);
          //{ GetSomething: { Response: ... }, CreateSomething: "{ Id: 8 }", RefreshSomething: "OK" , ...} 
          ...
          // do whatever you want
      });
```

**Usage with Javascript**
```javascript
const ParalellPromises = require('paralell-promises');

...

const concurrentLimit = 5;

const listOfPromises = [
      {
        name: 'GetSomething',
        function: this.operationWrapper.getSomethingFunction,
        thisArg: this.operationWrapper,
        args: ["firstParamForFunction",{ data: "Another param"}, ["more params..."]]
      },
      {
        name: 'CreateSomething',
        function: this.createSomething,
        thisArg: undefined,
        args: ["firstParamForFunction"]
      },
      {
        name: 'RefreshSomething',
        function: this.updateSomething,
      },
      ... 
      ]

      ParalellPromises.customPromiseAll(listOfPromises, concurrentLimit).then((result: IAnyObject)=>{
          console.log(result);
          //{ GetSomething: { Response: ... }, CreateSomething: "{ Id: 8 }", RefreshSomething: "OK" , ...} 
          ...
          // do whatever you want
      });
```

## Contributing
There is no plan regarding contributions in this project
## Credits
This NPM package has been developed by:

**Rafael Pernil Bronchalo** - *Developer* 

* [github/rafaelpernil2](https://github.com/rafaelpernil2)

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
