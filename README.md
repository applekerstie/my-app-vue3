# my-app-vue3

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## 1.

```
sudo apt-get remove nodejs npm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm

nvm --version
0.39.3
```

### 2.

```sh
nvm install 12.22.9
nvm install 16.20.0

nvm list

nvm use 16.20.0
Now using node v16.20.0 (npm v8.19.4)

참고)
nvm alias default 16.20.0
```

### 3. vite로 프로젝트 생성

```sh
npm init vue
Project name: … my-app-vue3
Add TypeScript? … No 
Add JSX Support? … No
Add Vue Router for Single Page Application development? … No 
Add Pinia for state management? … No
Add Vitest for Unit Testing? … No
Add an End-to-End Testing Solution?  No
Add ESLint for code quality? … Yes
Add Prettier for code formatting? … Yes
Add Vue DevTools 7 extension for debugging? (experimental) … No 

cd my-app-vue3
code .
```

### 4. 의존 라이브러리 생성

```sh
npm install
```

