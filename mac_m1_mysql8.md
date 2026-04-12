
### 安装mysql
brew install mysql@8.0

### 启动mysql
brew services start mysql@8.0

### 配置mysql环境变量
echo 'export PATH="/opt/homebrew/opt/mysql@8.0/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

### 设置账号密码
mysql_secure_installation
