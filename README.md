
---

#  Servidor Express com TypeScript

Este repositório contém a estrutura inicial para um projeto backend utilizando **Node.js**, **Express** e **TypeScript**, configurado com ambiente de desenvolvimento ágil usando `tsx`.

---

##  Pré-requisitos

Antes de começar, certifique-se de ter o **Node.js** (versão 18 ou superior) e o **npm** instalados em sua máquina.

---

##  Configuração do Ambiente

Siga os passos abaixo para preparar a estrutura e dependências do projeto.

1. **Inicializar o projeto Node.js:** Cria o arquivo package.json inicial.
Execute o comando no terminal para criar o `package.json`:

```bash
npm init -y

```


2. **Instalar dependências de desenvolvimento:** TypeScript, definições de tipos do Node e executador TSX.
Adicione as bibliotecas necessárias para suporte ao TypeScript e reexecução automática em ambiente de desenvolvimento:

```bash
npm i -D typescript @types/node tsx

```


3. **Inicializar a configuração do TypeScript:** Gera o arquivo tsconfig.json.
Crie o arquivo de configurações do compilador TypeScript:

```bash
npx tsc --init

```


4. **Instalar o Express:** Framework web e suas definições de tipos.
Instale o Express e os tipos correspondentes para autocompletar e checagem de tipos no código:

```bash
npm install express
npm install -D @types/express

```


5. **Criar a estrutura de pastas e arquivo principal:**
Crie o diretório `src` e o arquivo de entrada `app.ts`:

* **Linux/macOS:**

```bash
mkdir src && touch src/app.ts

```

* **Windows (PowerShell):**

```powershell
mkdir src; New-Item src/app.ts

```


---

##  Estrutura do Projeto

Após a criação dos arquivos e pastas, o projeto deverá ficar com a seguinte estrutura:

```text
meu-projeto-backend/
├── node_modules/
├── src/
│   └── app.ts
├── package.json
└── tsconfig.json

```

---

##  Código do Servidor

Cole o código a seguir no arquivo `src/app.ts`:

```typescript
// Importa a biblioteca Express e o tipo Express
// O Express será utilizado para criar o servidor web
import express from "express";
import type { Express } from "express";

// Cria uma aplicação Express
// A função express() devolve um objeto que representa o servidor da aplicação
const app: Express = express();

// Define a porta onde o servidor ficará disponível
const PORT: number = 8081;

// Inicializa o servidor utilizando a porta definida
// O método listen() faz o servidor começar a "escutar" requisições HTTP
app.listen(PORT, () => {
  console.log(`Servidor rodando em http://localhost:${PORT}`);
});

```

---

##  Configuração dos Scripts

Abra o arquivo `package.json` e adicione o script de desenvolvimento na seção `"scripts"`:

```json
"scripts": {
  "dev": "tsx watch src/app.ts"
}

```

---

## ▶ Executando o Servidor

Para iniciar o servidor em modo de desenvolvimento (com *live-reload* automático ao alterar os arquivos):

```bash
npm run dev

```

Se tudo estiver configurado corretamente, a seguinte mensagem aparecerá no terminal:

```bash
Servidor rodando em http://localhost:8081

```

---