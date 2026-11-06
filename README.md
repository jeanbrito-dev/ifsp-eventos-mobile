# IFSP Eventos — Mobile

Aplicativo de divulgação e acompanhamento de eventos do IFSP Caraguatatuba, para estudantes, servidores e comunidade.

## Stack

- React Native + Expo SDK 57
- TypeScript + Expo Router (navegação)
- NativeWind 4.2.7 + Tailwind CSS 3 (estilos)
- React Query + Axios (consumo e cache da API)
- React Hook Form + Zod (formulários)
- Expo SecureStore (armazenamento seguro de tokens)

> A instalação das dependências não implementa as telas ou a integração. Elas serão desenvolvidas pelos integrantes.

## Pré-requisitos

- Node.js 24 LTS, npm e Git
- Expo Go compatível com o SDK do projeto, ou ambiente de desenvolvimento Android/iOS
- API do projeto em execução para testar dados reais

## Instalação

```powershell
npm install
Copy-Item .env.example .env
npx expo-doctor
npx expo start -c
```

Abra o QR code com o Expo Go compatível. Para execução local com emulador, siga as instruções exibidas pelo Expo.

## Ambiente

`.env.example`:

```dotenv
EXPO_PUBLIC_API_URL=http://192.168.1.100:3000
```

Troque `192.168.1.100` pelo IP do computador com a API. O celular deve conseguir acessá-lo pela rede. Em dispositivo físico, `localhost` não é o computador da API.

**Atenção:** variáveis `EXPO_PUBLIC_` ficam acessíveis no aplicativo compilado; não coloque segredos nelas.

## Estrutura prevista

```text
app/            # Rotas e layouts do Expo Router
components/     # Componentes de UI compartilhados
src/
  features/     # Funcionalidades: auth, events, institutions, etc.
  services/     # Cliente HTTP
  hooks/        # Hooks reutilizáveis
  constants/    # Constantes e tema
global.css      # Diretivas do NativeWind
tailwind.config.js
metro.config.js
babel.config.js
```

Mantenha a convenção de `app/` ou `src/app/` gerada pelo template e ajuste o caminho de importação do `global.css` em `_layout.tsx`.

## Comandos úteis

```powershell
npx expo start
npx expo start -c
npx expo-doctor
npx tsc --noEmit
```

## Funcionalidades planejadas

- Entrada, login, registro e recuperação de senha
- Home, busca, detalhes e favoritos de eventos
- Instituições, seguidores e comentários
- Panorama IFSP: homenagens, calendário e documentos
- Perfil e configurações

## Contribuição

1. Crie uma branch a partir de `develop`: `feat/landing-page`, `feat/auth-screens`, etc.
2. Reutilize componentes e tokens visuais definidos pelo líder frontend.
3. Ao finalizar a tela, valide navegação, estados de erro e carregamento.
4. Abra PR para `develop` com imagens, testes realizados e link do cartão Trello.
5. Não faça push direto para `main` ou `develop`.

## Licença

A definir pela equipe antes da publicação pública.
