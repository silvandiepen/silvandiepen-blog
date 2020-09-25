---
date: 2020-09-25
---

# Using both npm and Yarn

Personally, I like to use npm, I don't really see a good reason why I would use Yarn. It could be faster, but I don't really feel it. So in all my personal projects I just use npm, but at my work, we use yarn. 

In some way I tend to keep using npm and it will create a `package-lock.json` file which could be added to the `.gitignore` but still. It give more complications than just that. So I need to force myself into using Yarn, which I am not a fan of.

So after years of thinking about doing it, I finally made a little script which just detects if the projects has a yarn.lock file and if so, it will use Yarn instead of npm.

```bash
alias serve='npmoryarn serve'
alias dev='npmoryarn dev'
alias start='npmoryarn start'
alias build='npmoryarn build'

function npmoryarn() {
  if [ -e yarn.lock ]; then
    yarn $@
  else
    npm run $@
  fi
}
```

Now I can just run `build` in my terminal and the terminal will figure out what to use. I actually had these commands in the aliases already, but just like `alias build=npm run build`. Which ofcourse, only works for projects using npm. Now I can just run the same command and not think about what to use.

