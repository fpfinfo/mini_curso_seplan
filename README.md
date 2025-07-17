# Mini Curso PWA

Este pacote contém os arquivos necessários para transformar seu "Mini Curso de Suprimento de Fundos" em um Progressive Web App (PWA).

## Conteúdo

- **manifest.json**: Configurações do PWA, incluindo nome, cores e ícones.
- **service-worker.js**: Script para cache offline básico.
- **icons/**: Pasta onde você deve adicionar seus ícones PWA (192x192 e 512x512).
- **README.md**: Este arquivo, com instruções de integração.

## Instruções de Integração

1. Coloque `manifest.json` e `service-worker.js` na mesma pasta que seu `index.html`.
2. Adicione o seguinte dentro da tag `<head>` do seu `index.html`:
   ```html
   <link rel="manifest" href="manifest.json" />
   <meta name="theme-color" content="#003366" />
   ```
3. Antes de fechar a tag `</body>`, adicione:
   ```html
   <script>
     if ('serviceWorker' in navigator) {
       window.addEventListener('load', () => {
         navigator.serviceWorker.register('service-worker.js')
           .then(reg => console.log('ServiceWorker registrado', reg))
           .catch(err => console.log('ServiceWorker falhou', err));
       });
     }
   </script>
   ```
4. Coloque seus ícones em `icons/icon-192x192.png` e `icons/icon-512x512.png`.
5. Sirva via HTTPS e teste em seu navegador.

