# Create From Template

To create a project from a specific template, supply the template name like so:

```
golem new <my-project> <template-name>
```

**NOTE:** For expediency, the create command does not initialize your test ship for the project. Once you have a project, you can initialize it with:

```
cd <my-project>
golem init
```

This should take a few minutes to run.

#### Some Available Templates:

**CRUD (DB) Template**

This template provides sur, lib, and mar files for one datatype and uses them in the `on-poke` and `on-peek` arms of the agent. The setup is meant to be easily extensible either by adding properties or additional data types.

```
golem new <my-project> crud
cd <my-project>
golem init
golem build
```

**Sail (CRM) Template**

This template includes all the piping in the CRUD template as well as an opinionated setup for serving Sail UI from the same agent, including separation of UI components into files.

```
golem new <my-project> sail
cd <my-project>
golem init
golem build
```

**Shrub Template (developer alpha Q3 '24)**

This template includes the \`%neo\` and \`%base\` dependencies needed to run shrubbery's developer alpha as well as an example shrub in a separate folder that you can start modifying right away to get hacking.

<pre><code><strong>golem new &#x3C;my-project> shrub
</strong>cd &#x3C;my-project>
golem init
golem build
</code></pre>

