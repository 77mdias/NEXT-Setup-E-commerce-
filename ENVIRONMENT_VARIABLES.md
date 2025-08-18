# Variáveis de Ambiente Necessárias

Para que a autenticação funcione corretamente, você precisa configurar as seguintes variáveis de ambiente:

## Banco de Dados

```
DATABASE_URL="postgresql://username:password@localhost:5432/mystore"
DIRECT_URL="postgresql://username:password@localhost:5432/mystore"
```

## NextAuth

```
NEXTAUTH_SECRET="your-secret-here"
NEXTAUTH_URL="http://localhost:3000"  # ou sua URL de produção
```

## Provedores OAuth (opcionais)

```
GITHUB_ID="your-github-client-id"
GITHUB_SECRET="your-github-client-secret"
GOOGLE_CLIENT_ID="your-google-client-id"
GOOGLE_CLIENT_SECRET="your-google-client-secret"
```

## Stripe

```
STRIPE_SECRET_KEY="sk_test_..."
STRIPE_WEBHOOK_SECRET_KEY="whsec_..."
```

## Remove.bg (opcional)

```
REMOVE_BG_API_KEY="your-remove-bg-api-key"
```

## Como obter as chaves OAuth:

### GitHub:

1. Vá para https://github.com/settings/applications/new
2. Crie uma nova OAuth App
3. Authorization callback URL: `http://localhost:3000/api/auth/callback/github`

### Google:

1. Vá para https://console.cloud.google.com/
2. Crie um novo projeto ou selecione um existente
3. Ative a Google+ API
4. Crie credenciais OAuth 2.0
5. Authorized redirect URIs: `http://localhost:3000/api/auth/callback/google`

## Gerando NEXTAUTH_SECRET:

```bash
openssl rand -base64 32
```
