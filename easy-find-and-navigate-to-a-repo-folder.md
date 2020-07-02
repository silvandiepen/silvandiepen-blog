# Easy find and navigate to a repository folder

Switching projects, finding folders. Every time I'm typing my ass of to open the folder, so I made a faster solutions which automatically finds a folder in my defined repos folder.
Add this to your bash_profile and use a simple command to go to your repo folder.

I started with a little shortcut just to go to my repos folder. Which is in my root, it's not that long, but it makes it easier.

```bash
repos(){
    if [ -z "$1" ]
        then
        cd $REPOS
    else
        # check if the folder exists
        if [ -d $REPOS/$1 ]
            then
            cd $REPOS/$1
        else
            #Check if the folder Does exist with an underscore
            if [ -d $REPOS/_$1 ]
                then
                cd $REPOS/_$1
            else
                if [[ -n $(find $REPOS -type d -maxdepth 2 -name $1) ]]
                    then
                    for i in $(find $REPOS -type d -maxdepth 2 -name $1);
                        do
                        cd "$i"
                    done
                else
                    echo $1 "folder doesn't exist"
                fi
            fi
        fi
    fi
}
```


- Obviously... change `~/repos` into your own local</li>
- Go to your local repos folder with the command `repos`
- Go to a local repo with the command `repos NameOfProject`
- This script searches for the folder in the first level and second level. Third level projects won't be found.
- This script automatically also searches for folder with a underscore `_` in front of the name.  (for ex. `repos projects` will also navigate to `_projects`

I have been using this code for a few years now and really implement it asap on a new device otherwise I really miss it. The code could probably be a lot better, but it works.
