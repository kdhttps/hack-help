# Node Startup Application

Our goal is to make REST API Application in NodeJS from this tutorial. 

1. Open terminal(command prompt) and run below commands to make startup application.

    Make first new folder.
    ```
    $ mkdir startup-app
    $ cd startup-app
    ```
    
    Run below command. Feel free to press enter key on every step.   
    ```
    $ npm init
    ```
    
    It will create package.json in current directory. For now just remember, it store the node dependency name and versions which we used during NodeJS application development.

2. Now create `index.js` file in current folder. Run below command.
   
    ```
    $ touch index.js
    ```
    
    Open file in any text editor or IDE. Add some below statement and save.
    ```
    const foo1 = 10;
    const foo2 = 20;
    console.log('Output: ',foo1 + foo2);
    ```
    
    After saving, back to your terminal and Run below command.
    ```
    $ node index.js
    ```
    
    Output:
    ```
    Output:  30
    ```   
    Node is compiler who compiles and execute your javascript files.

3. Now let's make REST API.

    First we need some node dependencies, which helps us to make REST full application. Run below commands.
    ```
    $ npm install --save express
    ```   
    
    Now back to your index.js in your editor and past below code.
    ```
    // call the dependencies we need
    var express    = require('express'); // call express
    var app        = express();          // define our app using express
    
    var port = 8000;                     // set our port
    
    // ROUTES FOR OUR API
    // ====================================================================
    var router = express.Router(); // get an instance of the express Router
    
    // test route to make sure everything is working 
    // (accessed at GET http://localhost:8080/api)
    router.get('/', function(req, res) {
        res.json({ message: 'Cool! Application started' });   
    });
    
    // more routes for our API will happen here
    
    // REGISTER OUR ROUTES
    // all of our routes will be prefixed with /api
    app.use('/api', router);
    
    // START THE SERVER
    // ====================================================================
    app.listen(port);
    console.log('Your application started on port ' + port);
    ```
    
    Now back to your terminal and run index.js.
    
    ```
    $ node index.js
    ```
    
    Output: 
    ```
    Your application started on port 8000
    ```
    
    Your application is running. Test it in browser URL: [http://localhost:8000/api](http://localhost:8000/api)
