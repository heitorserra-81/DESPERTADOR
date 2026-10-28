# Alvorada – Despertador com missões

Protótipo funcional (PWA) de um app de despertador com missões matinais, sequência de dias (streak), histórico e notificações. Funciona em Android e iOS pelo navegador e pode ser instalado na tela inicial.

## O que já funciona
- Cadastro e login (local, com senha em hash SHA-256)
- Alarmes: criar, editar, excluir, ativar/desativar, dias da semana, soneca de 5 min
- Missões para desligar: contas rápidas, digitar frase, respiração (segurar 10 s)
- Sequência de dias com meta e recorde, histórico e gráfico dos últimos 7 dias
- Notificações do navegador e vibração, modo offline (service worker)

## Como testar
1. Abra `index.html` no navegador, ou publique no GitHub Pages (veja abaixo).
2. Crie uma conta e use **Testar missão agora** na tela Hoje.
3. Use **Carregar dados de exemplo** no Perfil para ver sequência e histórico.

## Publicar no GitHub Pages
1. Envie esta pasta para um repositório (branch `main`).
2. Em **Settings → Pages**, escolha **Source: GitHub Actions**.
3. O workflow `.github/workflows/pages.yml` publica a cada push.
4. No celular: abra o link e use **Adicionar à tela inicial**.

## Limitações do protótipo (e próximos passos)
- Os dados ficam só no aparelho (localStorage). Para produção: backend com Supabase ou Firebase (auth, banco, sincronização).
- O alarme só toca com o app aberto. Para alarmes confiáveis em segundo plano é preciso app nativo (Expo/React Native ou Flutter, com notificações locais e, no iOS 26+, AlarmKit).
- Para publicar na Play Store e na App Store, empacote com Capacitor ou reescreva em Expo, reaproveitando este design e a lógica de missões.
