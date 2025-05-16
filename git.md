### git based configs

1. Clone repo with submodules fetching:  
   `$> git clone --recurse-submodules git@github.com:makeitfine-org/renovation.git`
> [!Note]  
> The above command will also download submodule `wiki`.  
> To make changes into `wiki` submodule generate access token in github:  
> Developer Settings &rarr; Personal access tokens (classic) &rarr; Generate new token

* * Add `wiki` submodule separately:  
    `$> git clone https://github.com/makeitfine-org/renovation.wiki.git wiki`  
    `$> git submodule add https://github.com/makeitfine-org/renovation.wiki.git wiki`  
    `$> git submodule update --init --recursive`

* * Work with submodule:  
    pull changes:  
    `$> git submodule update --remote`  
    pull and merge/rebase:  
    `$> git submodule update --remote --merge`  
    `$> git submodule update --remote --rebase`

* * Remove submodule `wiki`:  
    `$> git submodule deinit -f wiki`  
    `$> rm -rf wiki`  
    `$> rm -rf .git/modules/wiki`  
    `$> git config -f .gitmodules --remove-section submodule.wiki`  
    `$> git config -f .git/config --remove-section submodule.wiki`  
    `$> git rm --cached wiki`  
    `$> git commit -m 'rm submodule: wiki`

> [!Tip]
> More about submodules:    
> https://www.youtube.com/watch?v=wTGIDDg0tK8&ab_channel=AntonPutra  
> https://www.freecodecamp.org/news/how-to-use-git-submodules/

2. First after cloning repo config githook for project run gradle task from the root:  
   `$> gradle installGitHooks`
