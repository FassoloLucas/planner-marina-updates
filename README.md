# Planner — distribuição de atualizações

Este repositório público contém somente o manifesto de atualização e, futuramente, APKs publicados em Releases. O código fonte permanece privado.

## Estado atual

Ainda não há APK ou release publicado. O manifesto update.json declara available: false. Isso evita anunciar uma atualização que não possa ser baixada.

## Publicação futura

1. Gerar e verificar o APK do Planner com identificador com.marina.planner, a mesma chave das instalações existentes e versionCode crescente.
2. Confirmar que o APK contém a funcionalidade de atualização e passou pela validação no dispositivo.
3. Criar uma Release versionada e anexar o APK. Os downloads serão públicos, sem login.
4. Calcular o SHA-256 e o tamanho em bytes do APK efetivamente anexado.
5. Atualizar update.json por último, com schemaVersion: 1, available: true, packageName, versionCode, versionName, apkUrl, sha256 e sizeBytes. notes é opcional.
6. A URL apkUrl deve apontar diretamente para o APK da Release, em HTTPS. Não usar a página HTML da Release.

O aplicativo compara versionCode, baixa somente após o toque em Atualizar, verifica o arquivo e encaminha ao instalador do Android. A instalação exige confirmação da pessoa e pode exigir autorização para instalar desta fonte.

Não publicar código fonte, tokens, chaves de assinatura, backups ou dados pessoais neste repositório. Nunca colocar tokens GitHub no aplicativo.