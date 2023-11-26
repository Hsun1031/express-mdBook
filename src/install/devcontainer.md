# 安裝

建立專案資夾

```bash
mkdir my-project
cd my-project
```

`ctrl+shift+p` 或 `F1` 開啟命令列，輸入 `Remote-Containers: Add Development Container Configuration Files...`，選擇 `Node.js`，會在專案資料夾建立 `.devcontainer` 資料夾，裡面有 `Dockerfile` 和 `devcontainer.json`。

修改 `Dockerfile` 和 `devcontainer.json`。

`ctrl+shift+p` 或 `F1` 開啟命令列，輸入 `Remote-Containers: Reopen in Container`，會自動建立 docker image 和 container，並進入 container。

## 安裝 Express

```bash
yarn add express
# or use
npm install express
```

## 初始化專案

```bash
yarn init
# or 快速建立
yard init -y
```

## 修改指令
package.json
```json
{
  "scripts": {
    "start": "node index.js"
  }
}
```

建立 index.js
