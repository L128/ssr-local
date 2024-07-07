## ssr-local
Built with Apple Silicon for Surge support

#SOP:
git clone https://github.com/ShadowsocksR-Live/shadowsocksr-native.git

mv shadowsocksr-native ssr-n

cd ssr-n

git checkout 0.9.0 //Later versions will not build ssr-local

git submodule update --init

git submodule foreach -q 'git checkout $(git config -f $toplevel/.gitmodules submodule.$name.branch || echo master)'

cmake . && make ssr-local
