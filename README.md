# OneNpmPackagePerDay

## Background
2021 Sep, I was first learning front dev, and the task is to build a reagent validate platform.
To be honest, my old view about front dev is HTML/CSS, and I have no idea how Javascript make some cool change to broswer(at that time I don't understand is called DOM)
When my leader give a copy of current front code, I was Shocked and what a hell? full of .vue and npm packages(in node_modules).
vue components/vue-router/vuex/moment/axios/element-ui/vue-cli/webpack/babel....It took me a long time to self-study these concepts.When fininsh the platform I mentioned eariler, I think It's a great opportunity to learn dive these cool things and make me feel home in front ecosysytem.
So, maybe I will update some packages I learned and gradually rub these things in a project with front and backend.

## Original Intention
- record: npm packages, front ecosystem, cool tips
- practise skills: vue.js, node.js, gin, mongodb, etc 

## Directory
1. `cli`: if u want to create a cli tools, like `webpack-cli`, `vue-cli`, `lessc`, u will be look at this directory;
2. `connectivity`: provide some network standard packages and base tools like websocket, message queue, socket, port, etc;
3. `doc`: swagger? js-doc? if u create a app, these tools will ease u;
4. `env`: development/staging/testing/CI-CD/production environments and paired configuration;
5. `file`: temporary directories and data-base file tools;
6. `function`: util functions, maybe functional programming;
7. `log`: absolutely will be considered;
8. `orm`: store data will be use this, u will not directly connect database and should use these middle toolchains;
9. `security`: password hashing? encry/decry information?
10. `testing`: no more words;
11. `validation`: oh, more appear as plugins in some frameworks, for example, validate request or some user given information;