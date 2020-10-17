#Cf . Setup of asciidoc on wsl 

## install ruby on wsl

### rbenv install
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

### setup  rbenv and alias to .bashrc.
mkdir -p /mnt/c/dev/git/adocs/private
echo "alias cdp='cd /mnt/c/dev/git/adocs/private'" >> ~/.bashrc
echo "export PATH='$HOME/.rbenv/bin:$PATH'" >> ~/.bashrc
echo "eval '$(rbenv init -)'" >> ~/.bashrc
tail ~/.bashrc

### setup C compiler
sudo apt install build-essential libssl-dev libreadline-dev zlib1g-dev

### install ruby via rbenv
* インストール可能な Ruby のバージョンを確認
rbenv install -l
* eg.
CONFIGURE_OPTS='--disable-install-rdoc' rbenv install 2.7.2

## asciidoctorのインストール
gem install asciidoctor
gem install --pre asciidoctor-pdf
gem install coderay
gem install asciidoctor-pdf-cjk

cf. https://qiita.com/tamikura@github/items/5d3f62dae55617ee42bb#asciidoctor-asciidoctor-pdf%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB