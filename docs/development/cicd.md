# 如何建立自己的个人博客

基于 GitHub Actions + Netlify 的自动化文档流水线

### 概览
- **本地开发**：在 VSCode 中编写 Markdown 文档，使用 MkDocs 进行本地构建和预览。
- **版本控制**：通过 Git 管理文档变更。
- **自动化构建与部署**：GitHub Actions 自动构建，Netlify 自动部署。
- **持续集成/持续部署 (CI/CD)**：无需手动操作，只需推送代码，网站就会自动更新。

### 准备工作
> Vscode + Git + Python <br>
> Github + Netlify <br>
> MkDocs

### 步骤一
#### 在vscode创建本地文件夹并初始化git

```bash
mkdir my-docs 
cd my-docs # 创建一个名为 my-docs 的文件夹并进入

git init # 初始化 Git 仓库

mkdir docs
mkdir .github
mkdir .github/workflows # 创建基本的文档项目结构
```

#### 创建文档结构

```bash
my-docs/
├── docs/
│   ├── index.md # md格式首页文档
│   └── page1.md 
├── .github/
│   └── workflows/
└── mkdocs.yml # MkDocs配置文件
```
MkDocs配置文件如下：

```bash
site_name: 个人博客
nav:
    - 首页: index.md
    - 第一页: page1.md

theme:
    name: material  # 使用主题
```
### 步骤二
#### 创建Github账户
创建账户并登录后，添加New Repository，不用初始化仓库（勾选Add a ReadmeFile等）。

#### 创建Netlify账户并获取Auth Token
创建账户后，选择头像 -> User Settings -> Applications -> Add new access token -> Generate token。<br>
复制token。

### 步骤三 关联本地与远程仓库
在vscode终端将本地仓库与远程仓库关联
```bash
git remote add origin https://github.com/你的用户名/my-docs.git # clone自己的仓库地址

git branch -M main # 将本地的 main 分支推送到远程 origin 仓库，并设置上游追踪
git push -u origin main
```
### 步骤四 配置自动化
#### 创建 GitHub Actions 工作流文件
在VSCode .github/workflows/ 目录下创建一个新文件，命名为 ci-cd.yml。
```bash
name: CI/CD for Documentation

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Set up Python
      uses: actions/setup-python@v5
      with:
        python-version: '3.x'

    - name: Install dependencies
      run: |
        pip install mkdocs
        pip install mkdocs-material

    - name: Build documentation
      run: mkdocs build --strict

    - name: Deploy to Netlify
      uses: netlify/actions/cli@master
      with:
        args: deploy --prod --dir=site
      env:
        NETLIFY_AUTH_TOKEN: ${{ secrets.NETLIFY_AUTH_TOKEN }}
        NETLIFY_SITE_ID: ${{ secrets.NETLIFY_SITE_ID }}
```

#### 在 GitHub 上配置 Secrets
- 配置`NETLIFY_AUTH_TOKEN`<br>
进入Github my_docs仓库，进入Settings -> Secrets and variables -> Actions -> New repository secret。<br>
Name: `NETLIFY_AUTH_TOKEN`; Value: 步骤二复制的`Auth Token` <br>

- 配置`NETLIFY_SITE_ID`<br>
进入Netlify，选择Import an existing project，GitHub授权。<br>
在配置界面：Build command: `mkdocs build`；Publish directory: `site`，点击deploy site。
回到这个site details页面，找到并复制Site ID。
重复步骤一，再次add New repository secret。Name: `NETLIFY_SITE_ID`; Value: 刚刚复制的`Site ID`。

### 步骤五 测试与验证
修改md文件活任意一个文件，在vscode commit changes，或者在终端提交并推送这个更改：
```bash
git add docs/index.md
git commit -m "测试：添加新功能项以触发CI/CD"
git push origin main
```
若推送成功，可在GitHub Actions界面看到工作日志，并在Netlify看到网站URL。

### 其他 本地预览

```bash
pip install mkdocs mkdocs-material
mkdocs serve
```