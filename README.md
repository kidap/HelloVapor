# Swift + Vapor + Heroku

### Install Vapor
```
$ brew install vapor/tap/vapor
```

### Create Vapor sample project
```
$ vapor new HelloVapor --branch=beta
```

### Open project in XCode
```
$ cd HelloVapor
$ vapor xcode
```
Run -> My Mac

### Push project to Github
```
$ git add -A
$ git commit -m "Push to remote"
$ git push -u origin master
```

### Install swiftenv
https://swiftenv.fuller.li/en/latest/installation.html
```
$ git clone https://github.com/kylef/swiftenv.git ~/.swiftenv
```

For ZSH:
```
$ echo 'export SWIFTENV_ROOT="$HOME/.swiftenv"' >> ~/.zshenv
$ echo 'export PATH="$SWIFTENV_ROOT/bin:$PATH"' >> ~/.zshenv
$ echo 'eval "$(swiftenv init -)"' >> ~/.zshenv
```

### Use Swift 4.1 snapshot for this project
```
$ swiftenv local 4.1
```

Confirm version 
```
$ swiftenv version
4.1 (set by /<path>/HelloVapor/.swift-version)
```

### Connect to Heroku
```
$ heroku auth:login
Enter your Heroku credentials:
Email: <email address>
Password: ***************
Logged in as <email address>
```

### Create the app in Heroku. 
Use buildpack `https://github.com/kylef/heroku-buildpack-swift`
```
$ vapor heroku init
Would you like to provide a custom Heroku app name?
y/n> y
Custom app name:
> <app name>
Would you like to deploy to a region other than the US?
y/n> n
https://<app name>.herokuapp.com/ | https://git.heroku.com/<app name>.git

Would you like to provide a custom Heroku buildpack?
y/n> y
Custom buildpack:
> https://github.com/kylef/heroku-buildpack-swift
Setting buildpack...
Are you using a custom Executable name?
y/n> n
Setting procfile...
Committing procfile...
Would you like to push to Heroku now?
y/n> y
This may take a while...
Building on Heroku ... ~5-10 minutes
```
