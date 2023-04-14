## Project 4 - MEAN STACK IMPLEMENTATION

# MEAN Stack is a combination of following components:

MongoDB (Document database) – Stores and allows to retrieve data.
Express (Back-end application framework) – Makes requests to Database for Reads and Writes.
Angular (Front-end application framework) – Handles Client and Server Requests
Node.js (JavaScript runtime environment) – Accepts requests and displays results to end user



ubuntu@ip-172-31-35-240:~$ mkdir Books && cd Books
ubuntu@ip-172-31-35-240:~/Books$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (books) booksproject
version: (1.0.0) 
description: A simple book register app
entry point: (index.js) server.js
test command: 
git repository: 
keywords: 
author: Darey.io
license: (ISC) MIT
About to write to /home/ubuntu/Books/package.json:

{
  "name": "booksproject",
  "version": "1.0.0",
  "description": "A simple book register app",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Darey.io",
  "license": "MIT"
}


Is this OK? (yes) yes
ubuntu@ip-172-31-35-240:~/Books$ ls
package.json
ubuntu@ip-172-31-35-240:~/Books$ vi server.js
ubuntu@ip-172-31-35-240:~/Books$ sudo npm install express mongoose
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN notsup Unsupported engine for mongoose@7.0.3: wanted: {"node":">=14.0.0"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: mongoose@7.0.3
npm WARN notsup Unsupported engine for kareem@2.5.1: wanted: {"node":">=12.0.0"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: kareem@2.5.1
npm WARN notsup Unsupported engine for bson@5.2.0: wanted: {"node":">=14.20.1"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: bson@5.2.0
npm WARN notsup Unsupported engine for mongodb@5.1.0: wanted: {"node":">=14.20.1"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: mongodb@5.1.0
npm WARN notsup Unsupported engine for mquery@5.0.0: wanted: {"node":">=14.0.0"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: mquery@5.0.0
npm WARN notsup Unsupported engine for whatwg-url@11.0.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: whatwg-url@11.0.0
npm WARN notsup Unsupported engine for tr46@3.0.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: tr46@3.0.0
npm WARN notsup Unsupported engine for webidl-conversions@7.0.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: webidl-conversions@7.0.0
npm WARN booksproject@1.0.0 No repository field.

+ express@4.18.2
+ mongoose@7.0.3
added 81 packages from 102 contributors and audited 81 packages in 4.96s

8 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

ubuntu@ip-172-31-35-240:~/Books$ mkdir apps && cd apps
ubuntu@ip-172-31-35-240:~/Books/apps$ vi routes.js
ubuntu@ip-172-31-35-240:~/Books/apps$ cat vi routes.js
cat: vi: No such file or directory
var Book = require('./models/book');
module.exports = function(app) {
  app.get('/book', function(req, res) {
    Book.find({}, function(err, result) {
      if ( err ) throw err;
      res.json(result);
    });
  }); 
  app.post('/book', function(req, res) {
    var book = new Book( {
      name:req.body.name,
      isbn:req.body.isbn,
      author:req.body.author,
      pages:req.body.pages
    });
    book.save(function(err, result) {
      if ( err ) throw err;
      res.json( {
        message:"Successfully added book",
        book:result
      });
    });
  });
  app.delete("/book/:isbn", function(req, res) {
    Book.findOneAndRemove(req.query, function(err, result) {
      if ( err ) throw err;
      res.json( {
        message: "Successfully deleted the book",
        book: result
      });
    });
  });
  var path = require('path');
  app.get('*', function(req, res) {
    res.sendfile(path.join(__dirname + '/public', 'index.html'));
  });
};

ubuntu@ip-172-31-35-240:~/Books/apps$ mkdir models && cd models
ubuntu@ip-172-31-35-240:~/Books/apps/models$ vi book.js
ubuntu@ip-172-31-35-240:~/Books/apps/models$ cd ../..
ubuntu@ip-172-31-35-240:~/Books$ mkdir public && cd public
ubuntu@ip-172-31-35-240:~/Books/public$ vi script.js
ubuntu@ip-172-31-35-240:~/Books/public$ vi index.html
ubuntu@ip-172-31-35-240:~/Books/public$ cd ..
ubuntu@ip-172-31-35-240:~/Books$ node server.js
/home/ubuntu/Books/node_modules/mongodb/lib/operations/add_user.js:16
        this.options = options ?? {};
                                ^

SyntaxError: Unexpected token ?
    at Module._compile (internal/modules/cjs/loader.js:723:23)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Module.require (internal/modules/cjs/loader.js:692:17)
    at require (internal/modules/cjs/helpers.js:25:18)
    at Object.<anonymous> (/home/ubuntu/Books/node_modules/mongodb/lib/admin.js:4:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
ubuntu@ip-172-31-35-240:~/Books$ sudo npm install mongoose
npm WARN notsup Unsupported engine for mongoose@7.0.3: wanted: {"node":">=14.0.0"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: mongoose@7.0.3
npm WARN notsup Unsupported engine for bson@5.2.0: wanted: {"node":">=14.20.1"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: bson@5.2.0
npm WARN notsup Unsupported engine for kareem@2.5.1: wanted: {"node":">=12.0.0"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: kareem@2.5.1
npm WARN notsup Unsupported engine for mquery@5.0.0: wanted: {"node":">=14.0.0"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: mquery@5.0.0
npm WARN notsup Unsupported engine for mongodb@5.1.0: wanted: {"node":">=14.20.1"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: mongodb@5.1.0
npm WARN notsup Unsupported engine for whatwg-url@11.0.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: whatwg-url@11.0.0
npm WARN notsup Unsupported engine for tr46@3.0.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: tr46@3.0.0
npm WARN notsup Unsupported engine for webidl-conversions@7.0.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
npm WARN notsup Not compatible with your version of node/npm: webidl-conversions@7.0.0
npm WARN booksproject@1.0.0 No repository field.

+ mongoose@7.0.3
updated 1 package and audited 81 packages in 2.414s

8 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

ubuntu@ip-172-31-35-240:~/Books$ node server.js
/home/ubuntu/Books/node_modules/mongodb/lib/operations/add_user.js:16
        this.options = options ?? {};
                                ^

SyntaxError: Unexpected token ?
    at Module._compile (internal/modules/cjs/loader.js:723:23)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Module.require (internal/modules/cjs/loader.js:692:17)
    at require (internal/modules/cjs/helpers.js:25:18)
    at Object.<anonymous> (/home/ubuntu/Books/node_modules/mongodb/lib/admin.js:4:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
ubuntu@ip-172-31-35-240:~/Books$ node server.js
