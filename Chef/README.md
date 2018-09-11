
# Basic

```
chef generate cookbook cookbooks/{cookbook}
chef generate template cookbooks/{cookbook}/ {file}
```

Enable whyrun mode with *-W, --why-run*
```
chef-client --local-mode -Fmin -W --runlist 'recipe[{cookbook}::{recipe}]'
```


```
chef-client --local-mode --runlist 'recipe[{cookbook}::{recipe}]'
```

# My cookbook
Cookbook [webdev](cookbooks/webdev) can be used by Vagrant.
It has two recipes:
1. [packages.rb](cookbooks/webdev/recipes/packages.rb)
2. [users.rb](cookbooks/webdev/recipes/users.rb)
