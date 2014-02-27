This hook checks to see wether you are on one of your organizations' repositories and ensures that you are committing with the correct e-mail address.


## Installation

In *~/.gitconfig*, set your template dir:

```
[init]
    templatedir = ~/.git_template
```

Then copy the script *pre-commit* to *~/.git_template/hooks/*. This will assure that new repos created with either `clone` or `init` will have the hook. If you want it for an existing repo, then copy the script manually to *~/.git/hooks/*.


## Configuration

Configure the e-mail you want to use for your organization:

```bash
$ git config --global orgs.<your-org>.email <your-email>
```

You could also configure it manually in *~/.gitconfig*:

```
[orgs "<your-org>"]
    email = <your-email>
```

## Usage

If you have the e-mail **coyote@acme.org** configured for organization **acme**, and your current repo has at least one remote pointing to one of **acme**'s repos, then you will see this when you try to commit for the first time:

```
Organization 'acme' identified!
Setting the configured e-mail <coyote@acme.org>
Please repeat the commit command to use the new e-mail
```
