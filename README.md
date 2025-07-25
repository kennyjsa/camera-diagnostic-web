# 📷 Camera Diagnostic Web

Uma ferramenta simples em HTML + JavaScript para realizar diagnósticos de câmera diretamente no navegador. Ideal para suporte técnico ou testes de compatibilidade com APIs de mídia (WebRTC).

## 🚀 Funcionalidades

- Detecta todas as câmeras conectadas (`videoinput`).
- Coleta:
  - Nome, ID e tipo do dispositivo.
  - Capabilities, settings e constraints de cada câmera.
  - Permissões de câmera e microfone.
  - Informações do navegador, sistema operacional e idioma.
- Apresenta um log simulado estilo terminal com status das operações.
- Envia os dados para o Netlify Forms para armazenamento e análise posterior.

## 🧪 Fluxo de uso

1. O usuário acessa `index.html`.
2. Clica em `Iniciar Diagnóstico`.
3. O sistema testa o acesso às câmeras, coleta informações e exibe os logs.
4. Após o diagnóstico, o botão `Enviar Diagnóstico` é habilitado.
5. Os dados são enviados via formulário oculto para o painel do Netlify.
6. O usuário é redirecionado para uma tela de agradecimento.

## 🗂 Estrutura

```

camera-diagnostic-web/
├── index.html         # Página principal com o diagnóstico
├── thankyou.html      # Tela de agradecimento após envio
├── README.md          # Este arquivo

```

## 🧾 Campos enviados para o Netlify Forms

| Campo                 | Descrição                                             |
|----------------------|--------------------------------------------------------|
| `debugId`            | Timestamp de execução para rastreamento               |
| `deviceDate`         | Data/hora do dispositivo                              |
| `elapsedTimeMs`      | Tempo total do diagnóstico                            |
| `browserName`        | Nome do navegador (Chrome, Firefox, etc)              |
| `browserVersion`     | Versão do navegador                                   |
| `os`                 | Plataforma/SO (via `navigator.platform`)              |
| `language`           | Idioma configurado no navegador                       |
| `supportsMediaDevices` | Suporte a `getUserMedia`                            |
| `permissionsCamera`  | Estado da permissão da câmera (`granted`, etc.)       |
| `permissionsMicrophone` | Estado da permissão do microfone                  |
| `cameraCount`        | Quantidade de câmeras detectadas                      |
| `cameraInfo`         | JSON com dados detalhados das câmeras                 |
| `errors`             | JSON com mensagens de erro (se houver)                |

## 🧑‍💻 Deploy

Este projeto pode ser publicado diretamente no [Netlify](https://www.netlify.com/) com suporte nativo a Forms.

1. Faça push para um repositório no GitHub.
2. Conecte seu repositório no Netlify.
3. Acesse o projeto: `https://seu-projeto.netlify.app`

## 🛡️ Requisitos

- Navegadores modernos com suporte a WebRTC.
- Permissão concedida para acessar dispositivos de vídeo.

## 📄 Licença

MIT
