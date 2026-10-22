# Mister Movie — Configuração pública de contingência

Este repositório público contém apenas metadados de divulgação e downloads. **Nunca armazenar segredos, keystore, senhas, dados dos assinantes, webhooks, links de checkout editáveis ou regras de licença aqui.**

## Endereços estáveis

- Índice: https://raw.githubusercontent.com/synanimadigital-ops/mister-movie-downloads./main/config/v1/public.json
- WhatsApp e QR: https://raw.githubusercontent.com/synanimadigital-ops/mister-movie-downloads./main/config/v1/share.json
- Carrossel: https://raw.githubusercontent.com/synanimadigital-ops/mister-movie-downloads./main/config/v1/carousel.json
- APK: https://github.com/synanimadigital-ops/mister-movie-downloads./releases/latest/download/Mister.Movie.apk

## Regras de continuidade

1. No Android, consultar esses arquivos **fora da thread principal** com timeout, limite de tamanho, HTTPS e cache local. Nunca travar splash, Home ou player por falha de rede.
2. Sempre oferecer fallback aos recursos locais; se GitHub falhar, utilizar o último JSON validado armazenado no aparelho.
3. Carrossel: preservar o carrossel nativo; não remover recomendações/filmes; exibir em Premium e gratuito.
4. Publicar arte WebP antes de incluir sua URL em carousel.json. Usar HTTPS e validar tamanho/tipo/hash quando aplicável.
5. Mudanças de comunicação não mudam pagamentos, identidade do aparelho, Premium nem destinatário Stripe.
6. Migração Cloudflare/Railway exige backend separado, confirmação segura Stripe, sincronização idempotente das licenças e atualizador Android testado. GitHub não pode ativar Premium.
7. Para mudanças de roteamento financeiro, utilizar metadados autenticados criptograficamente e verificação no aplicativo, **fora desses JSON públicos**.
8. Antes de atualizar JSON de produção: criar backup da versão anterior, conferir JSON, testar no aparelho e preparar reversão por commit.

## Situação inicial

A configuração foi publicada para preparar infraestrutura. **O APK 50102 atual ainda não foi atualizado para consumi-la.** O carrossel de GitHub começa vazio por segurança: banners precisam ser publicados efetivamente, nunca inventar URLs. O QR e a mensagem usam o endereço de distribuição já aprovado.
