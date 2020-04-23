# Starter desk

## Installation

### Packages

#### cURL
```bash
sudo apt-get update \
sudo apt-get install curl
```

#### vim
```bash
sudo apt-get update \
sudo apt-get install vim
```

#### git
```bash
sudo apt-get update \
sudo apt-get install git-core
```

#### subversion
```bash
sudo apt-get update \
sudo apt-get install subversion
```

#### fish
```bash
sudo apt-add-repository ppa:fish-shell/release-2
sudo apt-get update
sudo apt-get install fish

#oh-my-fish
curl -L https://get.oh-my.fish | fish
```

### Applications

#### Filezilla
```bash
sudo apt-get update \
sudo apt-get install filezilla
```

#### Atom
```bash
wget -qO- https://atom.io/download/deb atom.deb \
sudo dpkg -i atom.deb
```

#### VS Code
```bash
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'

sudo apt-get update
sudo apt-get install code # or code-insiders
```

#### GitKraken
```bash
wget -qO- https://www.gitkraken.com/download/linux-deb gitkraken.deb \
sudo dpkg -i gitkraken.deb
```

#### Spotify
```bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 0DF731E45CE24F27EEEB1450EFDC8610341D9410 \
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list \
sudo apt-get update \
sudo apt-get install spotify-client
```

#### Google Chrome
```bash
echo deb https://dl.google.com/linux/chrome/deb/ stable main | sudo tee /etc/apt/sources.list.d/google-chrome.list \
sudo apt-get update \
sudo apt-get install google-chrome-stable
```

#### Firefox
```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C1289A29 \
echo deb http://downloads.sourceforge.net/project/ubuntuzilla/mozilla/apt all main | sudo tee /etc/apt/sources.list.d/firefox.list \
sudo apt-get update \
sudo apt-get install firefox-mozilla-build
```

### Outils

#### Composer
```bash
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer;
```

#### Drush
```bash
sudo sh -c "curl -L https://s3.amazonaws.com/files.drush.org/drush.phar > /usr/local/bin/drush" \
sudo chmod +x /usr/local/bin/drush \
drush init -y
```

#### WP-cli
```bash
sudo sh -c "curl -L https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar > /usr/local/bin/wp" \
sudo chmod +x /usr/local/bin/wp
```

```bash
sudo sh -c "curl -L https://raw.githubusercontent.com/wp-cli/wp-cli/master/utils/wp-completion.bash > /etc/bash_completion.d/wp-completion"
```
#### Phpcs avec le standard Drupal
```bash
# Facultatif
composer global require "hirak/prestissimo:^0.3" --prefer-dist --no-progress --no-suggest --optimize-autoloader --classmap-authoritative  --no-interaction

# Processus
composer global require drupal/coder:^8.2.12
composer global require dealerdirect/phpcodesniffer-composer-installer
```

### Docker

#### Docker
```bash
DOCKER_VERSION=`svn ls https://github.com/rancher/install-docker.git/branches/master | grep -E "^(0|[1-9][0-9]*)" | tail -1`
wget -qO- https://releases.rancher.com/install-docker/${DOCKER_VERSION} | sh
```

#### Docker-compose
```bash
COMPOSE_VERSION=`git ls-remote --tags https://github.com/docker/compose | tail -1 | grep -oP "(0|[1-9][0-9]*)\.(0|[1-9][0-9]*)\.(0|[1-9][0-9]*)"`
sudo sh -c "curl -L https://github.com/docker/compose/releases/download/${COMPOSE_VERSION}/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose"
sudo chmod +x /usr/local/bin/docker-compose
sudo sh -c "curl -L https://raw.githubusercontent.com/docker/compose/${COMPOSE_VERSION}/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose"
```

#### Ctop
```bash
RELEASE_VERSION=`git ls-remote --tags https://github.com/bcicen/ctop | tail -1 | grep -oP "(0|[1-9][0-9]*)\.(0|[1-9][0-9]*)\.(0|[1-9][0-9]*)"`
sudo wget https://github.com/bcicen/ctop/releases/download/v${RELEASE_VERSION}/ctop-${RELEASE_VERSION}-linux-amd64 -O /usr/local/bin/ctop
sudo chmod +x /usr/local/bin/ctop
```

#### Portainer
```bash
docker run --name portainer -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer:/data portainer/portainer
```

#### Adminer
```bash
docker run \
    --name local_adminer \
    -d \
    -p 8080:80 \
    -v /var/lib/mysql:/var/lib/mysql \
    -v /var/run/mysqld:/var/run/mysqld \
    clue/adminer
```
