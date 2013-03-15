Skel
====

A quick'n'dirty tool to generate project skeletons from a template.

    skel --- Generates an skeleton for a project.

    Usage:
      skel <kind>           Generates a new project of the given kind.
      skel help             Displays this screen.


## Templates

Templates are just folders in your `~/.skel` directory, with the following
structure:

    + /<name>
    |--o skeleton
    |--o DESCRIPTION
    `--+ template/
    
When you run `skel <name>`, the script will copy everything under the
`template` directory to the current directory. If a `skeleton` executable file
exists, that'll be used to post-process the copied files. `DESCRIPTION` is just
a plain text file telling `skel` what the template is all about.


## Skeleton

Skeleton files are used to post-process things that were copied from the
template. The scripts are executed at two different phases, with two different
arguments:

  - `skeleton setup` - Used before template variable replacements are done, in
    order to define the environment variables for replacement.
    
  - `skeleton post-process` - Used after template variable replacements are
    done, to do all sorts of things (for example, create a github repository).
    

## Requirements

Currently it requires PERL for the templating.


## Installation

Just copy the `skel` file and put it somewhere in your `PATH`.


## Licence

MIT/X11.
