# NVM vs NPM vs Yarn

* **NVM** is a node.js version manager. It provides easy installation, switching between versions and retains globally installed packages for each version. 
* **NPM** is a package manager, which help you install libraries, plugins, frameworks and applications.
* **Yarn** is another package manager to automate the process of installing, upgrading or removing software. The main difference between NPM and Yarn is the package installation process. Yarn installs packages in parallel. Yarn is optimized to fetch and install multiple packages at once.
  
# Node.js
Node.js is a JavaScript runtime environment for server-side development. Node.js allows you to write JavaScript code that runs on the server instead of in the browser. Node.js is popular for creating web applications, APIs, and microservices.

Pros:
* Performance: Node.js is known for its high performance. This is because Node.js uses an event-driven, non-blocking I/O model.
* Scalability: Node.js is very scalable and can be used to create large and complex applications.

Cons:
* Callback: Node.js can lead to callback issues if not used correctly. Callback issues are where too many nested callbacks make the code difficult to read and debug.  
* Single Threaded: Node.js is a single-threaded language that can only use one CPU core at a time. This can be a bottleneck for CPU-intensive tasks.

## EventLoop WorkerPool
* the Event Loop executes the JavaScript callbacks registered for events, and is also responsible for fulfilling non-blocking asynchronous requests like network I/O.
* Node.js uses the Worker Pool to handle "expensive" tasks. This includes I/O for which an operating system does not provide a non-blocking version, as well as particularly CPU-intensive tasks.

You should make sure you never block the Event Loop. In other words, each of your JavaScript callbacks should complete quickly.

## Basic Commands

To see list of commands:
* NPM - npm
* Yarn - yarn

Install dependencies from package.json:
* NPM - npm install
* Yarn - yarn

Install a package and add to package.json:
* NPM - npm install package --save
* Yarn - yarn add package

Install a devDependency:
* NPM - npm install package --save-dev
* Yarn - yarn add package --dev

Remove a dependency:
* NPM - npm uninstall package --save
* Yarn - yarn remove package

Upgrade a package to its latest version:
* NPM - npm update --save
* Yarn - yarn upgrade

Install a package globally:
* NPM - npm install package -g
* Yarn - yarn global add package


# Next Gen Javascript (ES)6)

## Arrow Functions

    const add = (a: number) => {...}; // kein function Keyword notwendig
    const add = (a: number, b: nummber) => a + b; // implizit return

## Default Function Parameters

     const add = (a: number, b: nummber = 1) => a + b;
     add(2); // nur noch das erste Argument ist notwendig, ABER: Argumente mit Defaultwerten müssen immer RECHTS stehen!

## Spread Operator
* zieht die Elemente aus einem Array und kopiert sind in ein neues Array
* kann auch einzelne Objekte in ein neues Object kopieren


    const hobbies = ['Sports', 'Cooking'];
    const activeHobbies = [];
    activeHobbies.push(...hobbies);

## Rest Operator
unbestimmte Anzahl an Parametern

    const toArray = (...args)  => {
        return args;
    }
    toArray(1,2,3,4);

## Destructuring
* rausziehen nur der benötigten properties aus Objekt


    cpnst person = {
        name: 'xxx',
        age: 25
    }
    const printName = ({name}) => {
        console.log(name);
    }
    printName(person);

* bei Arrays:
    

    const hobbies = ['sports','cooking'];
    const [hobby1, hooby2] = hobbies;

## Closures

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

# Typescript

Types: number, string, boolean, object, array, enum, any, union, literal, undefined, function, unknown, never

Type aliase - used to created own types

    type User = { name: string; age: number };

## Decorators = Meta Programming
Decorator = Function
Decorators laufen, wenn JS die konstruktor function definition findet

## Compile

    tsc --watch //watchmode, recompile after change
    tsc --init // create tesconfig.json with compiler options

## Variables
    
    const = Konstante
    let = Variable (let hat var ersetzt, weil in JS var auch auf globaler Ebene registriert wurde, auch wenn es lokal innerhalb einer Funktion definiert wurde)

# Webpack

    npm install --save-dev webpack webpack-cli webpack-dev-server typescript ts-loader


# NodeJS

NodeJs kennt nur JS kein TS, es ignoriert Dateiendungen (.js, .ts) und versucht jeden Dtaie als JS auszuführen

# Jest
TestingFramework, TestRunner, AssertionLibrary with Matchers
with TS support

global methods:
* describe
* test
* expect

## Initialize Jest

    npx ts-jest config:init --> initialisiert config.ts

initialize with config.ts manually

# Libs & Frameworks
* loopback
* express
* axios - Promise based Http client
* 

## Testing Libs & Framewoks
* sinon
* mocha
* jest
* chai


