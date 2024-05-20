# Build & Serve

Once you are in the project folder you can build the test envs by running:
```
cd <my-project>
golem build
```
Once this is run, you can find your desk installed in a test ship at `http://localhost`, the UI will still need to be globbed for it to show up, but you can confirm the desk installation by visiting `http://localhost/docket/upload` and finding it in the dropdown. Use the form on that page to upload the contents of the `/<my-project>/ui` folder and you should be able to test it.
