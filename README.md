## The usual suspects

* Install `homebrew`
* Install `brew-cask`
* Install [`yeoman`](http://yeoman.io/)

> **Note:** keep an eye on [Bedrock](http://roots.io/wordpress-stack/) as a stack setup.


## Build local environment

```bash
brew cask install virtualbox

brew cask install vagrant

git some git@github.com:Automattic/vip-quickstart.git

./bin/vip-init
```

**Requires access to WordPress SVN to sync developer plugins**

> * `Updating Shared VIP plugins`  Checks for WordPress.com username at https://vip-svn.wordpress.com:443

Let's try [VVV](https://github.com/10up/varying-vagrant-vagrants) by 10up instead:

```bash
vagrant plugin install vagrant-hostsupdater

git some git://github.com/10up/varying-vagrant-vagrants.git vagrant-local

cd vagrant-local

vagrant up
```

> **Note:** look into how to have more than one VM set up this way. Possibly [vvv-init](https://github.com/cftp/vvv-init/)?


## Install starter theme/framework

```bash
cd www/wordpress-default/wp-content/themes
```

Use [_s](https://github.com/automattic/_s) to start until custom baseline can be developed.

_Try using [Yeoman _s generator](https://github.com/kdo/generator-wp-underscores)_

```bash
npm install -g generator-wp-underscores

mkdir theme-name && cd $_
yo wp-underscores

grunt
```

> **Note:** [Roots](http://roots.io/starter-theme/) and [Bones](http://themble.com/bones/) are worth a look too.

Hacked a few bits out of the Roots starter theme with success. Modularity of template files, some sensible functions, and a clean directory structure. Just wish it didn't come with Bootstrap baked-in.



## Develop custom theme/site

Following [FED standards](https://github.com/tidaltheory/frontend-code-standards/wiki), of course. Either develop theme in `/wp-content/themes` directly, or in a separate location/repository and include in `/wp-content/themes` as a submodule.

```bash
grunt
bower
```

> **Hardcore mode:** [Genesis Framework](http://www.genesisframework.com/) + [Dynamik Website Builder](http://cobaltapps.com/downloads/dynamik-website-builder/) + [Toolset](http://wp-types.com/)


## Deploy to Staging environment and test/demo

```bash
git-ftp? capistrano? grunt? 
```

Tried `grunt-ftp-deploy` which worked well enough (as long as you were careful with the ignore settings) although not really suited for use whilst developing, as it doesn't track file changes and uploads the entire project each time. `grunt-git-ftp` could be an option, or possibly [Dandelion](http://scttnlsn.github.io/dandelion/), both of which use git to track changes.


## Package finished theme for deployment

```bash
grunt
```


## Deploy to Production environment

```bash
git-ftp? capistrano? grunt? 
```

