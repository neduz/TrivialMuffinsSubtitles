# 0. Submodules
The subtitles for each play are located as branches in a submodule. Please do not forget to run 
```
git submodule init
git submodule update
```

# 1. Requirements
- Node.js and its package manager npm

# 2. Node.js packages

The following commands install the necessary Node.js packages. To run the communication server, `websockets` and `hashmap` is needed.
For the reconnecting clients (Master, Slave, Prompter), reconnect-core and browserify is needed (for development only). 
Run this in the directory where the .js files are.

```
npm install http-server websocket hashmap reconnect-core browserify
```

# 3. Development
You can edit {Master,Slave,Prompter,Server}.js, {Master,Slave,Prompter}.html and Boventiteling.css to develop the subtitler.
When any of the browser-running javascript files is editted (i.e. {Master,Slave,Prompter}.js) run `./Bundle` to update the {Master,Slave,Prompter}-bundle.js files.

# 4. Deploy
- Edit the file Master.js to configure the filename it will read, look for a line like this:
pipeParser("CurrentPlay/Arsenic and Old Lace subtitles - combined.csv", parseData);
- run `./Bundle` generates the files needed to run in web-browser.
- `./Server` runs Server.js in node and starts a http-server listening on port 8000.


# 5. Usage
- Go to http://localhost:8000/Master.html on your home screen
- Show http://localhost:8000/Slave.html on your projection screen
- Use the Master.html page to control the projection screen.
