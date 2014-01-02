## The usual suspects

* Install `homebrew`
* Install `brew-cask`
* Install [`yeoman`](http://yeoman.io/)


## Build local environment

```bash
brew cask install virtualbox

brew cask install vagrant

git some git@github.com:Automattic/vip-quickstart.git

./bin/vip-init
```

**Running into problems at this point; could be due to Vagrant/VirtualBox/Mavericks incompatibilities.**

> * `Updating Shared VIP plugins`  Checks for WordPress.com username at https://vip-svn.wordpress.com:443 - init script continues after three tries; might be needed though.
> * `Configuring the hosts file`  Prompts for password and will not accept. Need to edit /etc/hosts manually `10.86.73.80 vip.dev`

Let's try [VVV](https://github.com/10up/varying-vagrant-vagrants) by 10up instead:

```bash
vagrant plugin install vagrant-hostsupdater

git some git://github.com/10up/varying-vagrant-vagrants.git vagrant-local

cd vagrant-local

vagrant up
```


## Install base theme/framework

Use [_s](https://github.com/automattic/_s) to start until custom baseline can be developed.

```bash
cd www/wordpress-default/wp-content/themes
```
_Try using [Yeoman _s generator](https://github.com/kdo/generator-wp-underscores)_
```bash
npm install -g generator-wp-underscores

mkdir theme-name && cd $_
yo wp-underscores

grunt
```


## Develop custom theme/site
Following FED standards, of course.
```bash
grunt
bower
```


## Package finished theme for deployment

```bash
grunt
```


## Deploy to Staging environment and test/demo

```bash
git-ftp? capistrano? grunt? 
```


## Deploy to Production environment

```bash
git-ftp? capistrano? grunt? 
```

