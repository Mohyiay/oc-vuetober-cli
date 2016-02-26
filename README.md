# oc-vuetober-cli

A simple CLI for scaffolding Vuetober themes.

### Installation

Prerequisites: [Node.js](https://nodejs.org/en/) and [Git](https://git-scm.com/).

``` bash
$ npm install -g oc-vuetober-cli
```

### Usage

``` bash
$ vuetober init my-project
$ cd my-project
$ npm install
$ npm run dev
```

The above command pulls the template from [scottbedard/oc-vuetober-theme](https://github.com/scottbedard/oc-vuetober-theme), prompts for some information, and generates the project at `./my-project/`.

### Official Templates

The purpose of the official Vuetober theme template is to provide an opinionated, battery-included development tooling setups so that users can get started with actual app code as fast as possible.

### Custom Templates

It's unlikely to make everyone happy with the official templates. You can simply fork the official template and then use it via `oc-vuetober-cli` with:

``` bash
vuetober init username/repo my-project
```

Where `username/repo` is the GitHub repo shorthand for your fork.

The shorthand repo notation is passed to [download-git-repo](https://github.com/flipxfx/download-git-repo) so you can also use things like `bitbucket:username/repo` for a Bitbucket repo and `username/repo#branch` for tags or branches.

If you would like to download from a private repository use the `--clone` flag and the cli will use `git clone` so your SHH keys are used.

You can also create your own template from scratch:

- A template repo **must** have a `template` directory that holds the template files.

- All template files will be piped through Handlebars for simple templating - `oc-vuetober-cli` will automatically infer the prompts based on `{{ }}` interpolations found in the files.

- A template repo **may** have a `meta.json` file that provides a schema for the prompts. The schema will be passed to [prompt-for](https://github.com/segmentio/prompt-for#prompt-for) as options. See [example](https://github.com/vuejs-templates/webpack/blob/master/meta.json).

While developing your template you can test via `oc-vuetober-cli` with:

``` bash
vuetober init ~/fs/path/to-custom-template my-project
```
