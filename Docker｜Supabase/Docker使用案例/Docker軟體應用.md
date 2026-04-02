
## OpenCode

Windows與WSL可共用

- API Key存在哪裡?  
  A：/root/.local/share

1. 創造一個持久化 opencode 的 volume  
   ```shell
   docker volume create opencode-auth
   ```
2. 每個 Project 使用一個 container  
   ```Shell
   docker run -it --rm -w /home \
  --entrypoint /bin/sh \
  -v ${PWD}:/home \
  -v opencode:/root/.local/share/opencode \
  ghcr.io/anomalyco/opencode
   ```

## uv（spec-kit）

1. 創造一個uv的container  
   ```shell
   docker run -it --name uv `
  -v uv:/root `
  -v ${PWD}:/home `
  ghcr.io/astral-sh/uv:debian bash
   ```
2. 安裝 spec-ki  
   ```shell
   uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
   ```
3. 安裝 SDD 於專案  
   ```shell
   specify init --ignore-agent-tools .
   ```
4. update  
   ```Shell
   docker run --rm --name uv `
  -v uv:/root `
  ghcr.io/astral-sh/uv:debian uv tool upgrade specify-cli
   ```

## Bun

## Node.JS
