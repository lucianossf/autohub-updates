# AutoHub Updates

Este repositório público é o canal de distribuição do AutoHub para Windows. Ele recebe os instaladores e os metadados usados pelo `electron-updater`; o código-fonte permanece no repositório privado [auto-gest-setup](https://github.com/lucianossf/auto-gest-setup).

## Como as atualizações funcionam

Ao iniciar, o AutoHub verifica se há uma versão mais recente. Quando encontra uma release publicada aqui, avisa o usuário, baixa o instalador em segundo plano e permite reiniciar o aplicativo para concluir a atualização.

O GitHub Actions do repositório de código compila backend, interface e instalador e publica nesta área quando uma tag de versão `v*` é enviada. A release deve incluir o instalador Windows e o manifesto `latest.yml`, sem token de acesso embutido no aplicativo.

## Estado da primeira publicação

O canal está configurado, mas ainda precisa da primeira release para que instalações existentes encontrem uma versão nova. A publicação inicial depende do secret `AUTOHUB_RELEASE_TOKEN` no repositório `auto-gest-setup`. As instruções estão no [README principal do projeto](https://github.com/lucianossf/auto-gest-setup#primeira-configura%C3%A7%C3%A3o-do-publicador).

Depois da primeira publicação, cada nova tag correspondente à versão em `autogest-exe/electron/package.json` dispara o build e a publicação automaticamente.
