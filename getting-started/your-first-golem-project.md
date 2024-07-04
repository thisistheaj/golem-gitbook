# Your First %golem Project

Great, you have golem installed! Now let's use golem to create a new app.

Starting from a folder where you keep your urbit projects you can create a new application using:

```
golem new my-project crud
```

The `new` command not only creates a project but it also gets all of the needed dependencies for building a basic project (namely, the `%garden` and `%base` desks)

In this command, `my-project` is the project name and we are using the template `crud` (Create, Read, Update, Delete). \
\
The crud agent template has a desk with all of the CRUD operations defined for one datatype, and it includes a react frontend for interacting with the agent.&#x20;

But we can't run it without a test ship to run it on, to create your test environment we need to `cd` in to the project and run `init:`

```
cd my-project
golem init
```

the `init` command will take a while to run — that is because it is creating a new test ship for you to use. it also fetches the latest urbit binary for you under the hood.

Once that is done running you should see a fakezod in your `/ships` folder:

```
ls ships
> zod urbit
```

It also has a copy of the urbit binary!

If you inspect the contents of zod, you will see that there is already a desk mounted for your app:

```
ls ships/zod
> my-project
```

But this desk doesn't have the files to run your project yet, and it also isn't even running. \
\
We need to `build` the project. But for our developpment flow, we also want to rebuild the project whenever we make changes to the code. So instead of running the `build` command, we will use `watch` to watch for filechanges and rebuild. We also want to see the debug output from our urbit ship, which we need the `shell` command for.\
\
To set this up, run the commands in the following order:

```
golem shell
```

then, open a **second terminal window** and run:

```
golem watch
```

Once you run this, make a change to any file and you should see the ship update in the dojo anytime golem is interacting with it. Namely, you should see the desk being commited and revived.&#x20;

Okay, now let's see the app in action. go to the url of your urbit (in this case: `localhost:10783/`)  and login. If you don't have the code, get it by going to the urbit terminal and running:

```
+code
> lidlut-tabwed-pillex-ridrup
```

You should see your app in landscape now, but it will have a spinner that says "installing". This is because it is waiting for you to upload the built UI to docket so it can serve the app. \
\
To upload it:

1. navigate to`localhost:10783/docket/upload`&#x20;
2. Select `my-project` from the dropdown
3. click "upload files" and navigate to the dist folder of your project (in this case `my-project/apps/my-project/ui/dist`) and select it for upload
4. Click "glob" — you should see a success mesaage after a few short moments

Now when you navigate back to the main page you should see your app finished installing. Click in and check out the UI.\
\
The CRUD template is a basic react UI that stores items in a list — but this data is saved in your new urbit app! \
\
Now that you're here you can start modifying the agent and UI tomake the app that you want.&#x20;

if you want to practice developing a gall app to get a feel for working with golem, here are some ideas for low-lift modifications to make to the template:

* right now the `item` datatype only has one prop — can you add more and update the UI accordingly to use the data?
* the crud tempate doesnt share anything with other ships by default — can you use updates and subscriptions in gall to share a list between two ships&#x20;
  * (**tip:** you can edit `./ships.json` in order to add additional fake ships to your test environment, just rerun `golem init` after you do and it will create any ships it finds that dont yet exist)
* Maybe you hate react and want to try using Vue insteaad (or somehting else) — can you replace the project in `/ui` with a different frontend?&#x20;
  * (**tip:** the only assumptions golem makes is the the ui is built with `npm run build` and that the build folder is named `./dist` )

Happy hacking!
