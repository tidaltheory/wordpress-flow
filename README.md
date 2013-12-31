## The usual suspects

* Install `homebrew`
* Install `brew-cask`


## Build local environment

```bash
brew cask install virtualbox

brew cask install vagrant

git some git@github.com:Automattic/vip-quickstart.git

./bin/vip-init
```
`Updating Shared VIP plugins` checks for WordPress.com username at https://vip-svn.wordpress.com:443 - init script continues after three tries; might be needed though.

> Running into problems at this point; could be due to Vagrant/VirtualBox/Mavericks incompatibilities.


## Install base theme/framework

```bash
yo
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

