# Nedis: downloads e atualizações

Este repositório publica os **instaladores e as atualizações** do aplicativo desktop do Nedis. Ele não contém código-fonte: serve só para distribuir as versões.

Site oficial: [nedis.com.br](https://nedis.com.br)

## Baixar

| Sistema | Arquivo | Download |
|---|---|---|
| Windows 10 e 11 (64 bits) | `Nedis-Setup.exe` | [Baixar](https://github.com/eupsa/nedis-releases/releases/latest/download/Nedis-Setup.exe) |
| macOS (Intel e Apple Silicon) | `Nedis.dmg` | [Baixar](https://github.com/eupsa/nedis-releases/releases/latest/download/Nedis.dmg) |
| Linux (AppImage) | `Nedis.AppImage` | [Baixar](https://github.com/eupsa/nedis-releases/releases/latest/download/Nedis.AppImage) |
| Linux (Debian e Ubuntu) | `Nedis.deb` | [Baixar](https://github.com/eupsa/nedis-releases/releases/latest/download/Nedis.deb) |

Os links acima apontam sempre para a **versão mais recente**. Para ver versões anteriores e as notas de cada uma, abra a aba [Releases](https://github.com/eupsa/nedis-releases/releases).

> Disponibilidade por sistema: o Windows é o primeiro a sair. Se o arquivo do seu sistema ainda não aparecer na última release, ele ainda não foi publicado.

## Como instalar

**Windows:** execute `Nedis-Setup.exe`, aceite a licença e conclua a instalação (ela pede permissão de administrador e instala para todos os usuários).

- Enquanto o instalador não tiver assinatura digital, o Windows SmartScreen pode mostrar "O Windows protegeu o computador". Clique em **Mais informações** e depois em **Executar assim mesmo**. Baixe sempre deste repositório ou do site oficial.

**macOS:** abra o `Nedis.dmg` e arraste o app para a pasta Aplicativos.

**Linux:** no AppImage, dê permissão de execução (`chmod +x Nedis.AppImage`) e abra. No `.deb`, instale com `sudo apt install ./Nedis.deb`.

## Como funcionam as atualizações

O app se atualiza sozinho:

1. Procura uma versão nova ao abrir e a cada 4 horas.
2. Baixa em segundo plano.
3. Avisa quando está pronta. Você pode escolher **Reiniciar para atualizar** no ícone da bandeja ou deixar para instalar quando fechar o app.

Você **não precisa** baixar nada de novo para atualizar. Só baixe um instalador daqui para instalar pela primeira vez ou reinstalar.

Os arquivos `latest.yml`, `latest-mac.yml`, `latest-linux.yml` e `*.blockmap` de cada release são lidos pelo atualizador do app e guardam as verificações de integridade. Não os apague nem os edite.

## Problemas

- O app não atualiza: confirme que há internet e que a versão instalada é anterior à última release. Reinstalar pelo link acima também resolve.
- Dúvidas, falhas e sugestões: use o suporte indicado no [site](https://nedis.com.br). Não publique dados pessoais, senhas ou códigos de verificação em issues deste repositório.

## Para quem publica (equipe)

As releases são criadas pelo `electron-builder` a partir do projeto do app desktop, com `npm run release:win` (ou `release:mac`, `release:linux`) e um `GH_TOKEN` com permissão de escrita neste repositório. Elas nascem como **rascunho**: o app só enxerga a versão depois de **Publish release**. Nunca altere os arquivos de uma release já publicada; publique uma versão nova (com `version` maior no `package.json`).
