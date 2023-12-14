no# Node

- Event Driven,
- Non-blocking I/O Model
- npm audit
- Node Interactive shell/REPL(Read Eval Print Loop) `node` in cmd
- Course Outline -> Nodejs. Basic -> Efficient Development -> express.js -> Templating Engines -> MVC -> Advanced Routes & Models -> MySQL -> Sequelize -> MongoDb -> Session & Cookies -> authentication -> Emails -> Authentication Deep Drive -> User input Validation -> error Handling -> File Upload & Downloads -> Pagination -> Async Request -> Payments -> REST API -> async -> Websocket/socket.io -> GraphQL -> Deployment -> Beyond Web Servers -> Typescript,Deno
- Create Node Server from Scratch

- Run node.js script from the command line `node app.js`
- How to exit from a Node.js program `process.exit(1)` 1 is integer be default it's 0
  you can set explicitly as `process.exitCode = 1`
  1 Uncaught Fatal Exception: There was an uncaught exception, and it was not handled by a domain or an 'uncaughtException' event handler.
  2 Unused (reserved by Bash for builtin misuse)
  3 Internal JavaScript Parse Error: The JavaScript source code internal in the Node.js bootstrapping process caused a parse error. This is extremely rare, and generally can only happen during development of Node.js itself.
  4 Internal JavaScript Evaluation Failure: The JavaScript source code internal in the Node.js bootstrapping process failed to return a function value when evaluated. This is extremely rare, and generally can only happen during development of Node.js itself.
  5 Fatal Error: There was a fatal unrecoverable error in V8. Typically a message will be printed to stderr with the prefix FATAL ERROR.
  6 Non-function Internal Exception Handler: There was an uncaught exception, but the internal fatal exception handler function was somehow set to a non-function, and could not be called.
  7 Internal Exception Handler Run-Time Failure: There was an uncaught exception, and the internal fatal exception handler function itself threw an error while attempting to handle it. This can happen, for example, if an 'uncaughtException' or domain.on('error') handler throws an error.
  8 Unused. In previous versions of Node.js, exit code 8 sometimes indicated an uncaught exception.
  9 Invalid Argument: Either an unknown option was specified, or an option requiring a value was provided without a value.
  10 Internal JavaScript Run-Time Failure: The JavaScript source code internal in the Node.js bootstrapping process threw an error when the bootstrapping function was called. This is extremely rare, and generally can only happen during development of Node.js itself.
  12 Invalid Debug Argument: The --inspect and/or --inspect-brk options were set, but the port number chosen was invalid or unavailable.
  13 Unfinished Top-Level Await: await was used outside of a function in the top-level code, but the passed Promise never resolved.
  > 128 Signal Exits: If Node.js receives a fatal signal such as SIGKILL or SIGHUP, then its exit code will be 128 plus the value of the signal code. This is a standard POSIX practice, since exit codes are defined to be 7-bit integers, and signal exits set the high-order bit, and then contain the value of the signal code. For example, signal SIGABRT has value 6, so the expected exit code will be 128 + 6, or 134.

Express is a framework that uses the http module under the hood, app.listen() returns an instance of http. You would use https.createServer if you needed to serve your app using HTTPS, as app.listen only uses the http module.

- How to read environment variables from Node.js > process.env.NODE_ENV

## REPL

- How to use the Node.js REPL > `node`
  REPL also known as Read Evaluate Print Loop is a programming language environment (basically a console window) that takes single expression as user input and returns the result back to the console after execution.
  Try entering the name of a JavaScript class, like Number, add a dot and press tab. The REPL will print all the properties and methods you can access on that class.
  You can inspect the globals you have access to by typing global. and pressing tab. If after some code you type \_, that is going to print the result of the last operation.
  The REPL has some special commands, all starting with a dot .. They are

.help: shows the dot commands help
.editor: enables editor mode, to write multiline JavaScript code with ease. Once you are in this mode, enter ctrl-D to run the code you wrote.
.break: when inputting a multi-line expression, entering the .break command will abort further input. Same as pressing ctrl-C.
.clear: resets the REPL context to an empty object and clears any multi-line expression currently being input.
.load: loads a JavaScript file, relative to the current working directory
.save: saves all you entered in the REPL session to a file (specify the filename)
.exit: exits the repl (same as pressing ctrl-C two times)

The REPL knows when you are typing a multi-line statement without the need to invoke .editor.

For example if you start typing an iteration like this:

[1, 2, 3].forEach(num => {
and you press enter, the REPL will go to a new line that starts with 3 dots, indicating you can now continue to work on that block.

... console.log(num)
... })
If you type .break at the end of a line, the multiline mode will stop and the statement will not be executed.

## Node.js, accept arguments from the command line

- node app.js
- node app.js joe
- node app.js name=joe

```javascript
process.argv.forEach((val, index) => {
  console.log(`${index}: ${val}`);
});
```

- const args = process.argv.slice(2)
- const args = process.argv.slice(2)
  args[0]

- node app.js name=joe
  args[0] is name=joe, and you need to parse it. The best way to do so is by using the minimist library, which helps dealing with arguments:

  const args = require('minimist')(process.argv.slice(2))
  args['name'] //joe

- This time you need to use double dashes before each argument name:

- node app.js --name=joe

- Command line Using Node.js
- `console.log(x,y)`
  console.log('My %s has %d years', 'cat', 2)
  %s format a variable as a string
  %d format a variable as a number
  %i format a variable as its integer part only
  %o format a variable as an object
- `console.clear()` clears the console (the behaviour might depend on the console used)
- console.count() is a handy method.

```javascript
const x = 1;
const y = 2;
const z = 3;
console.count(
  "The value of x is " + x + " and has been checked .. how many times?"
);
console.count(
  "The value of x is " + x + " and has been checked .. how many times?"
);
console.count(
  "The value of y is " + y + " and has been checked .. how many times?"
);
```

-

```javascript
const oranges = ["orange", "orange"];
const apples = ["just one apple"];
oranges.forEach((fruit) => {
  console.count(fruit);
});
apples.forEach((fruit) => {
  console.count(fruit);
});
```

- console.trace():

```javascript
const function2 = () => console.trace();
const function1 = () => function2();
function1();
```

- Calculate the time spent

```javascript
const doSomething = () => console.log("test");
const measureDoingSomething = () => {
  console.time("doSomething()");
  //do something, and measure the time it takes
  doSomething();
  console.timeEnd("doSomething()");
};
measureDoingSomething();
```

- console.error prints to the stderr stream.

- Color the output

  ```javascript
  console.log("\x1b[33m%s\x1b[0m", "hi!");
  ```

- You install it with npm install chalk, then you can use it:

```javascript
const chalk = require("chalk");
console.log(chalk.yellow("hi!"));
```

- Create a progress bar
  Progress is an awesome package to create a progress bar in the console. Install it using npm install progress

```javascript
const ProgressBar = require("progress");

const bar = new ProgressBar(":bar", { total: 10 });
const timer = setInterval(() => {
  bar.tick();
  if (bar.complete) {
    clearInterval(timer);
  }
}, 100);
```

- Accept input from the command line in Node.js

```javascript
const readline = require("readline").createInterface({
  input: process.stdin,
  output: process.stdout,
});

readline.question(`What's your name?`, (name) => {
  console.log(`Hi ${name}!`);
  readline.close();
});
```

> The question() method shows the first parameter (a question) and waits for the user input. It calls the callback function once enter is pressed.

- You can install it using npm install inquirer, and then you can replicate the above code like this:

```javascript
const inquirer = require("inquirer");

var questions = [
  {
    type: "input",
    name: "name",
    message: "What's your name?",
  },
];

inquirer.prompt(questions).then((answers) => {
  console.log(`Hi ${answers["name"]}!`);
});
```

> Inquirer.js lets you do many things like asking multiple choices, having radio buttons, confirmations, and more. It's worth knowing all the alternatives, especially the built-in ones provided by Node.js, but if you plan to take CLI input to the next level, Inquirer.js is an optimal choice.

- Expose functionality from a Node.js file using exports

- An introduction to the npm package manager
  npm update
  npm will check all packages for a newer version that satisfies your versioning constraints.
- `npm run <task-name>`
- `npm list`
- Use npm update --no-save to not update package.json.
- Update all the Node.js dependencies to their latest version

```bash
npm install -g npm-check-updates
ncu -u
npm update
```

- Uninstalling npm packages

```bash
 npm uninstall <package-name>
```

Using the -S flag, or --save, this operation will also remove the reference in the package.json file.

```Bash
npm uninstall -g <package-name>
```

You need to set the --production flag (npm install --production) to avoid installing those development dependencies.

- Creating a promise
  The Promise API exposes a Promise constructor, which you initialize using new Promise():

```javascript
let done = true;

const isItDoneYet = new Promise((resolve, reject) => {
  if (done) {
    const workDone = "Here is the thing I built";
    resolve(workDone);
  } else {
    const why = "Still working on something else";
    reject(why);
  }
});

const isItDoneYet = new Promise(/* ... as above ... */);
//...

const checkIfItsDone = () => {
  isItDoneYet
    .then((ok) => {
      console.log(ok);
    })
    .catch((err) => {
      console.error(err);
    });
};
```

> Running checkIfItsDone() will specify functions to execute when the isItDoneYet promise resolves (in the then call) or rejects (in the catch call).

- Fetch API

```javascript
const status = (response) => {
  if (response.status >= 200 && response.status < 300) {
    return Promise.resolve(response);
  }
  return Promise.reject(new Error(response.statusText));
};

const json = (response) => response.json();

fetch("/todos.json")
  .then(status) // note that the `status` function is actually **called** here, and that it **returns a promise***
  .then(json) // likewise, the only difference here is that the `json` function here returns a promise that resolves with `data`
  .then((data) => {
    // ... which is why `data` shows up here as the first parameter to the anonymous function
    console.log("Request succeeded with JSON response", data);
  })
  .catch((error) => {
    console.log("Request failed", error);
  });
```

- Handling errors
  In the example, in the previous section, we had a catch that was appended to the chain of promises.

When anything in the chain of promises fails and raises an error or rejects the promise, the control goes to the nearest catch() statement down the chain.

```javascript
new Promise((resolve, reject) => {
  throw new Error("Error");
}).catch((err) => {
  console.error(err);
});

// or

new Promise((resolve, reject) => {
  reject("Error");
}).catch((err) => {
  console.error(err);
});
```

- Cascading errors
  If inside the catch() you raise an error, you can append a second catch() to handle it, and so on.

```javascript
new Promise((resolve, reject) => {
  throw new Error("Error");
})
  .catch((err) => {
    throw new Error("Error");
  })
  .catch((err) => {
    console.error(err);
  });
```

- Orchestrating promises
  If you need to synchronize different promises, Promise.all() helps you define a list of promises, and execute something when they are all resolved.

```javascript
const f1 = fetch("/something.json");
const f2 = fetch("/something2.json");

Promise.all([f1, f2])
  .then((res) => {
    console.log("Array of results", res);
  })
  .catch((err) => {
    console.error(err);
  });

// The ES2015 destructuring assignment syntax allows you to also do

Promise.all([f1, f2]).then(([res1, res2]) => {
  console.log("Results", res1, res2);
});
```

- Promise.race() runs when the first of the promises you pass to it resolves, and it runs the attached callback just once, with the result of the first promise resolved.

Example:

```javascript
const first = new Promise((resolve, reject) => {
  setTimeout(resolve, 500, "first");
});
const second = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, "second");
});

Promise.race([first, second]).then((result) => {
  console.log(result); // second
});
```

- Modern Asynchronous JavaScript with Async and Await

```javascript
const doSomethingAsync = () => {
  return new Promise((resolve) => {
    setTimeout(() => resolve("I did something"), 3000);
  });
};

const doSomething = async () => {
  console.log(await doSomethingAsync());
};

console.log("Before");
doSomething();
console.log("After");

// Another
const getFirstUserData = () => {
  return fetch("/users.json") // get users list
    .then((response) => response.json()) // parse JSON
    .then((users) => users[0]) // pick first user
    .then((user) => fetch(`/users/${user.name}`)) // get user data
    .then((userResponse) => userResponse.json()); // parse JSON
};

getFirstUserData();

// vs
const getFirstUserData = async () => {
  const response = await fetch("/users.json"); // get users list
  const users = await response.json(); // parse JSON
  const user = users[0]; // pick first user
  const userResponse = await fetch(`/users/${user.name}`); // get user data
  const userData = await userResponse.json(); // parse JSON
  return userData;
};

getFirstUserData();
```

- Multiple async functions in series

```javascript
const promiseToDoSomething = () => {
  return new Promise((resolve) => {
    setTimeout(() => resolve("I did something"), 10000);
  });
};

const watchOverSomeoneDoingSomething = async () => {
  const something = await promiseToDoSomething();
  return something + "\nand I watched";
};

const watchOverSomeoneWatchingSomeoneDoingSomething = async () => {
  const something = await watchOverSomeoneDoingSomething();
  return something + "\nand I watched as well";
};

watchOverSomeoneWatchingSomeoneDoingSomething().then((res) => {
  console.log(res);
});
```

- The Node.js Event emitter

```javascript
const EventEmitter = require("events");
const eventEmitter = new EventEmitter();
eventEmitter.on("start", () => {
  console.log("started");
});
// When we run
eventEmitter.emit("start");
// With arguments
eventEmitter.on("start", (number) => {
  console.log(`started ${number}`);
});

eventEmitter.emit("start", 23);

// once(): add a one-time listener
// removeListener() / off(): remove an event listener from an event
// removeAllListeners(): remove all listeners for an event
```

- Build an HTTP Server

```javascript
const http = require("http");

const port = process.env.PORT;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader("Content-Type", "text/html");
  res.end("<h1>Hello, World!</h1>");
});

server.listen(port, () => {
  console.log(`Server running at port ${port}`);
});
// Other things
res.statusCode = 200;
res.setHeader("Content-Type", "text/html");
res.end("<h1>Hello, World!</h1>");
```

- Perform a GET Request

```javascript
const https = require("https");
const options = {
  hostname: "whatever.com",
  port: 443,
  path: "/todos",
  method: "GET",
};

const req = https.request(options, (res) => {
  console.log(`statusCode: ${res.statusCode}`);

  res.on("data", (d) => {
    process.stdout.write(d);
  });
});

req.on("error", (error) => {
  console.error(error);
});

req.end();
```

- Perform a POST Request

```javascript
const https = require("https");

const data = JSON.stringify({
  todo: "Buy the milk",
});

const options = {
  hostname: "whatever.com",
  port: 443,
  path: "/todos",
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "Content-Length": data.length,
  },
};

const req = https.request(options, (res) => {
  console.log(`statusCode: ${res.statusCode}`);

  res.on("data", (d) => {
    process.stdout.write(d);
  });
});
req.on("error", (error) => {
  console.error(error);
});

req.write(data);
req.end();
```

> PUT and DELETE requests use the same POST request format, and just change the options.method value.

- Make an HTTP POST request using Node.js

```javascript
const axios = require("axios");

axios
  .post("https://whatever.com/todos", {
    todo: "Buy the milk",
  })
  .then((res) => {
    console.log(`statusCode: ${res.statusCode}`);
    console.log(res);
  })
  .catch((error) => {
    console.error(error);
  });
```

- Get HTTP request body data using Node.js

```javascript
const axios = require("axios");

axios.post("https://whatever.com/todos", {
  todo: "Buy the milk",
});

// This is the matching server-side code:

const express = require("express");
const app = express();

app.use(
  express.urlencoded({
    extended: true,
  })
);

app.use(express.json());

app.post("/todos", (req, res) => {
  console.log(req.body.todo);
});

// Vanilla Nodejs
const server = http.createServer((req, res) => {
  // we can access HTTP headers
  req.on("data", (chunk) => {
    console.log(`Data chunk available: ${chunk}`);
  });
  req.on("end", () => {
    //end of data
  });
});

// Other

const server = http.createServer((req, res) => {
  let data = "";
  req.on("data", (chunk) => {
    data += chunk;
  });
  req.on("end", () => {
    console.log(JSON.parse(data).todo); // 'Buy the milk'
    res.end();
  });
});
```

- Working with file descriptors in Node.js
  A file descriptor is what's returned by opening the file using the open() method offered by the fs module:

```javascript
const fs = require("fs");

fs.open("/Users/joe/test.txt", "r", (err, fd) => {
  //fd is our file descriptor
});

// with openSync
const fs = require("fs");

try {
  const fd = fs.openSync("/Users/joe/test.txt", "r");
} catch (err) {
  console.error(err);
}
```

- Node.js file stats

```javascript
const fs = require("fs");
fs.stat("/Users/joe/test.txt", (err, stats) => {
  if (err) {
    console.error(err);
    return;
  }
  //we have access to the file stats in `stats`
});
// with sync
const fs = require("fs");
try {
  const stats = fs.statSync("/Users/joe/test.txt");
} catch (err) {
  console.error(err);
}
// Stats variable
const fs = require("fs");
fs.stat("/Users/joe/test.txt", (err, stats) => {
  if (err) {
    console.error(err);
    return;
  }

  stats.isFile(); //true
  stats.isDirectory(); //false
  stats.isSymbolicLink(); //false
  stats.size; //1024000 //= 1MB
});
```

- Node.js File Paths

```javascript
const notes = "/users/joe/notes.txt";

path.dirname(notes); // /users/joe
path.basename(notes); // notes.txt
path.extname(notes); // .txt

path.basename(notes, path.extname(notes)); // You can get the file name without the extension by specifying a second argument to basename:
```

> You can join two or more parts of a path by using path.join():

```javascript
const name = "joe";
path.join("/", "users", name, "notes.txt"); //
```

> You can get the absolute path calculation of a relative path using path.resolve():

```javascript
path.resolve("joe.txt"); //'/Users/joe/joe.txt' if run from my home fold
path.resolve("tmp", "joe.txt"); //'/Users/joe/tmp/joe.txt' if run from my home folder
path.resolve("/etc", "joe.txt"); //'/etc/joe.txt'
path.normalize("/users/joe/..//test.txt"); //'/users/test.txt'
```

- Reading files with Node.js

```javascript
const fs = require("fs");

fs.readFile("/Users/joe/test.txt", "utf8", (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});

// Alternate
const fs = require("fs");

try {
  const data = fs.readFileSync("/Users/joe/test.txt", "utf8");
  console.log(data);
} catch (err) {
  console.error(err);
}
```

- Writing files with Node.js

```javascript
const fs = require("fs");

const content = "Some content!";

fs.writeFile("/Users/joe/test.txt", content, (err) => {
  if (err) {
    console.error(err);
    return;
  }
  //file written successfully
});
// Alternate
const fs = require("fs");

const content = "Some content!";

try {
  const data = fs.writeFileSync("/Users/joe/test.txt", content);
  //file written successfully
} catch (err) {
  console.error(err);
}

// You can modify the default by specifying a flag:
// By default, this API will replace the contents of the file if it does already exist.
fs.writeFile("/Users/joe/test.txt", content, { flag: "a+" }, (err) => {});
```

- Append to a file
  A handy method to append content to the end of a file is fs.appendFile() (and its fs.appendFileSync() counterpart):

```javascript
const content = "Some content!";

fs.appendFile("file.log", content, (err) => {
  if (err) {
    console.error(err);
    return;
  }
  //done!
});
```

- Working with folders in Node.js
  Use fs.access() to check if the folder exists and Node.js can access it with its permissions.

```javascript
// Create a new folder
// Use fs.mkdir() or fs.mkdirSync() to create a new folder.

const fs = require("fs");

const folderName = "/Users/joe/test";

try {
  if (!fs.existsSync(folderName)) {
    fs.mkdirSync(folderName);
  }
} catch (err) {
  console.error(err);
}

// Read the content of a directory
// Use fs.readdir() or fs.readdirSync() to read the contents of a directory.

const fs = require("fs");

const folderPath = "/Users/joe";

fs.readdirSync(folderPath);

// You can get the full path:

fs.readdirSync(folderPath).map((fileName) => {
  return path.join(folderPath, fileName);
});

// Filter
const isFile = (fileName) => {
  return fs.lstatSync(fileName).isFile();
};

fs.readdirSync(folderPath)
  .map((fileName) => {
    return path.join(folderPath, fileName);
  })
  .filter(isFile);

// Rename a folder
// Use fs.rename() or fs.renameSync() to rename folder. The first parameter is the current path, the second the new path:

const fs = require("fs");

fs.rename("/Users/joe", "/Users/roger", (err) => {
  if (err) {
    console.error(err);
    return;
  }
  //done
});
// fs.renameSync() is the synchronous version:

const fs = require("fs");

try {
  fs.renameSync("/Users/joe", "/Users/roger");
} catch (err) {
  console.error(err);
}

// Remove a folder
// Use fs.rmdir() or fs.rmdirSync() to remove a folder.
// Removing a folder that has content can be more complicated than you need. You can pass the option { recursive: true } to recursively remove the contents.

fs.rmdir(dir, { recursive: true }, (err) => {
  if (err) {
    throw err;
  }

  console.log(`${dir} is deleted!`);
});
```

```bash
npm install fs-extra
```

```javascript
const fs = require("fs-extra");

const folder = "/Users/joe";

fs.remove(folder, (err) => {
  console.error(err);
});

// With Promise
fs.remove(folder)
  .then(() => {
    //done
  })
  .catch((err) => {
    console.error(err);
  });

// or with async/await:

async function removeFolder(folder) {
  try {
    await fs.remove(folder);
    //done
  } catch (err) {
    console.error(err);
  }
}

const folder = "/Users/joe";
removeFolder(folder);
```

## The Node.js fs module

```javascript
const fs = require("fs");
```

Once you do so, you have access to all its methods, which include:

fs.access(): check if the file exists and Node.js can access it with its permissions
fs.appendFile(): append data to a file. If the file does not exist, it's created
fs.chmod(): change the permissions of a file specified by the filename passed. Related: fs.lchmod(), fs.fchmod()
fs.chown(): change the owner and group of a file specified by the filename passed. Related: fs.fchown(), fs.lchown()
fs.close(): close a file descriptor
fs.copyFile(): copies a file
fs.createReadStream(): create a readable file stream
fs.createWriteStream(): create a writable file stream
fs.link(): create a new hard link to a file
fs.mkdir(): create a new folder
fs.mkdtemp(): create a temporary directory
fs.open(): set the file mode
fs.readdir(): read the contents of a directory
fs.readFile(): read the content of a file. Related: fs.read()
fs.readlink(): read the value of a symbolic link
fs.realpath(): resolve relative file path pointers (., ..) to the full path
fs.rename(): rename a file or folder
fs.rmdir(): remove a folder
fs.stat(): returns the status of the file identified by the filename passed. Related: fs.fstat(), fs.lstat()
fs.symlink(): create a new symbolic link to a file
fs.truncate(): truncate to the specified length the file identified by the filename passed. Related: fs.ftruncate()
fs.unlink(): remove a file or a symbolic link
fs.unwatchFile(): stop watching for changes on a file
fs.utimes(): change the timestamp of the file identified by the filename passed. Related: fs.futimes()
fs.watchFile(): start watching for changes on a file. Related: fs.watch()
fs.writeFile(): write data to a file. Related: fs.write()
One peculiar thing about the fs module is that all the methods are asynchronous by default, but they can also work synchronously by appending Sync.

For example:

fs.rename()
fs.renameSync()
fs.write()
fs.writeSync()

```javascript
const fs = require("fs");

fs.rename("before.json", "after.json", (err) => {
  if (err) {
    return console.error(err);
  }

  //done
});
// A synchronous API can be used like this, with a try/catch block to handle errors:
const fs = require("fs");

try {
  fs.renameSync("before.json", "after.json");
  //done
} catch (err) {
  console.error(err);
}

// The key difference here is that the execution of your script will block in the second example, until the file operation succeeded.
```
