# NEXUS Desktop — Instalador para Windows

Repositório público exclusivo para **distribuição dos instaladores oficiais do NEXUS Desktop**.

O código-fonte e os dados do aplicativo permanecem no repositório privado do NEXUS. Este repositório não deve conter senhas, tokens, código-fonte privado ou arquivos de configuração sensíveis.

## Versão Electron existente

O NEXUS Desktop **0.1.2** já foi compilado como instalador Windows x64 (`NEXUS-Setup-0.1.2-x64.exe`).

No momento, o pacote encontra-se em um **artefato temporário do GitHub Actions do repositório privado**. Isso significa que ele exige acesso ao repositório e não serve como download público para os usuários.

## Como publicar a versão oficial

1. No repositório privado do NEXUS, acesse o workflow Windows que gerou a versão 0.1.2.
2. Em **Artifacts**, baixe o arquivo ZIP `NEXUS-Desktop-Windows-Teste`.
3. Extraia e verifique o instalador `NEXUS-Setup-0.1.2-x64.exe` em um computador Windows. Confirme o tema atual, login, áudio e atualização do site.
4. Neste repositório público, abra **Releases → Draft a new release**.
5. Crie a tag `v0.1.2`, escolha um título como `NEXUS Desktop 0.1.2` e envie **apenas o instalador EXE** como anexo (asset).
6. Publique a release. O endereço público terá o formato:

   `https://github.com/rafaeliatestee-arch/instaladornexus/releases/download/v0.1.2/NEXUS-Setup-0.1.2-x64.exe`

   **Esse endereço só funcionará depois que o arquivo real for anexado à release.**

7. Registre o URL HTTPS real e a versão na tabela `public.nexus_desktop_releases` do Supabase, com `is_published=true`, para ativar o botão de download público do site.

### Conferência de integridade

No PowerShell:

```powershell
Get-FileHash .\NEXUS-Setup-0.1.2-x64.exe -Algorithm SHA256
```

Publique o hash na descrição da release. O instalador deve ser validado antes de distribuição pública.

### Sobre as atualizações

O aplicativo Electron atual abre a versão publicada do site NEXUS. As mudanças web aparecem depois da publicação no Lovable; atualizações do próprio Electron exigem um novo instalador.

**Status:** repositório de distribuição preparado; ainda não há EXE publicado neste repositório.
