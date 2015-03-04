# recipeutil
A tool that helps manage and manipulate `autopkg` recipes.

```
recipeutil verb [--parent|--all-parents] [--names] recipename|recipeid
```

##  verbs

### `info`
synonym for autopkg info

### `id` or `identifier`
shows the identifier for the recipe

### `which` or `path`
prints the path to the recipe

### `open`
uses the `open` command to open the recipe with the default application

### `edit`
opens the recipe with the `$EDITOR`. If the variable `$RECIPE_EDITOR` is set, this will be used instead

### `reveal`
reveals the recipe in finder

### `status`
shows `git status` of the file

### `cache`
opens the cache folder for this recipe in the Finder

### `clearcache`
deletes the cache folder for this recipe

### `duplicate`
will prompt for a new recipe identifier fill that in a new recipe

### `new`
will search the autopkg search path for recipes named RecipeTemplate.* and create a new recipe from that

### `newchild`
will create a new recipe pointed to the given recipe as parent. will use a RecipeTemplate if it can be found in the autopkg recipe search path

### `merge`
will create a new recipe by merging the given recipe with its parent

### `split`
will print the processors and prompt for a step to split the given recipe after. The original file will be retained with '_presplit' added to the filename.


## options

### `--parent` or `-p`
applies the verb to the recipe's parent

### `--all-parents` or `-a`
recursively applies verb to the recipe and all its parents

### `--names` or `-n`
prints the name of the recipe before the information

### extra arguments
`recipeutil` will pass through extra arguments to the `edit` and `status` actions, e.g.

```
recipeutil status Firefox.download --short

recipeutil edit --all-parents Fetch.munki --new-window
```

