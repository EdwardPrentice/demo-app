# demo-app



## Initial thoughts
Not a fan of the challenge. Makes me groan. Not sure what it meaningfully assesses, if anything

## Subsequent thoughts
Maybe I’ll learn something. Could be interesting. Proves I have a working dev setup

Starting
Yeoman seems to be the answer: https://stormpath.com/blog/angular-node-15-minutes

Installing software takes a few minutes. Will sign up to Github in the meantime - oh, I already have an account. Software is installed.

Running through the Yes No questions. Going well :) Also moved into a git repo ready to be Githubbed shortly. While npm install is running signing up to Heroku.

Turns out I don’t have a Heroku account and this bug has tripped up my npm install command: https://github.com/node-inspector/v8-debug/issues/30

http://stackoverflow.com/questions/33463945/node-pre-gyp-install-fallback-to-build-failed-during-meanjs-installation-on
Tried: npm install -g node-gyp
Didn’t work
https://github.com/node-inspector/v8-debug/issues/7
Tried: npm install -g grunt-node-inspector
Didn’t work
Tried npm install -g v8-debug From my own head
Didn’t work
Manual fix to the package.json and…. it worked! Only 20 minutes lost and now I have signed up to Heroku.

Now we can try the ```grunt serve``` and see if everything *did* actually work….!?

Whole bunch of SASS related errors. Going to start again and use CSS :)

http://stackoverflow.com/questions/8200622/how-to-remove-untracked-files-in-git : git clean -fdx

Back to the start.

While everything is installing again, switched guides to this guy: http://awaxman11.github.io/blog/2014/07/13/how-to-create-an-angular-app-using-yeoman-and-deploy-it-to-heroku/

Manual fix again to fix grunt-node-inspector

Everything installed. Let’s try grunt serve again…

Success! Allo Allo!

Now to push to git and push to Heroku before I start hacking at it.

Pushed to git. Asked me for my username and password. Wonder how to set that up properly with a key.

brew install heroku

quick bit of hacking, adding the web.js the Procfile, commiting.

git push heroku master *FINGERS CROSSED, RUNNING OUT OF TIME*

Says it worked….!!

A webpage with “Cannot GET /“ on it. Hmmm….

Ah yes! http://stackoverflow.com/questions/24566635/heroku-cannot-get The ```grunt build``` never actually worked.

    Total 434ms
    Warning: Running "imagemin:dist" (imagemin) task
    Fatal error: Path must be a string. Received { url: 'https://raw.github.com/imagemin/gifsicle-bin/v0.1.7/vendor/osx/gifsicle',
        name: 'gifsicle',
        os: 'darwin' }

So….. hmmm…..
https://github.com/angular-fullstack/generator-angular-fullstack/issues/765
hacking the package.json again….. didn’t work

https://github.com/npm/npm/issues/6051
npm install grunt-contrib-imagemin --save-dev
npm install -save-dev

Maybe 50 minutes in at this point

A new error message :)

    Warning: Running "imagemin:dist" (imagemin) task
    Fatal error: Cannot read property 'contents' of undefined

https://github.com/gruntjs/grunt-contrib-imagemin/issues/330
hacking the package.json again… didn’t work
Adding "vinyl-fs": "2.2.1" ….. didn’t work
npm install…….. grunt build…… No change.
Hack the package.json again..
npm cache clean; npm install; grunt build

It worked!

Let’s push to Heroku again…!!

hacking away with the web.js…. still doesn’t work. Maybe 30 minutes of hacking around with the web js.

That’s 1hr 45 minutes of following several tutorials and fighting with node to build and deploy a simple demo app


Perhaps if I have time, I will continue to wrestle with angular/heroku another day

