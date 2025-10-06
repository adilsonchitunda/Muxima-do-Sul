# Muxima do Sul - Comunicação & Relações Públicas

![Logo](public/assets/logo.png)

Um site moderno e responsivo para a Muxima do Sul, empresa líder em Comunicação e Relações Públicas sediada no Huambo, Angola.

## 🌟 Visão Geral

O site da Muxima do Sul é uma Single Page Application (SPA) construída com React e Firebase, projetada para apresentar os serviços da empresa, permitir interação com clientes e fornecer uma plataforma para gerenciamento de conteúdo.

### Funcionalidades Principais

- 🌐 **Multi-idioma**: Suporte para português e inglês
- 🔍 **Sistema de Busca**: Pesquise conteúdo em todo o site
- 💬 **Chat Widget com IA**: Interaja com três assistentes virtuais especializados
- ⭐ **Sistema de Feedback**: Avalie nossos serviços e deixe comentários
- 📱 **Design Responsivo**: Experiência perfeita em todos os dispositivos
- 🔧 **Painel Administrativo**: Gerencie todo o conteúdo do site facilmente
- 📊 **SEO Otimizado**: Melhor visibilidade nos mecanismos de busca

## 🚀 Demonstração

Domínio actual: [https://www.muximadosul.web.app](https://www.muximadosul.web.app).
Depois:
Acesse o site em: [https://www.muximadosul.com](https://www.muximadosul.com)

## 🛠️ Tecnologias Utilizadas

- **Frontend**: React 18, React Router DOM
- **Estilização**: CSS3 com variáveis customizadas
- **Backend**: Firebase (Firestore, Authentication)
- **Hospedagem**: Firebase Hosting
- **Gerenciamento de Pacotes**: npm, React Scripts

## 📦 Estrutura do Projeto

```
muxima-do-sul/
├── public/                    # Arquivos estáticos
│   ├── assets/               # Imagens e outros recursos
│   ├── sounds/               # Arquivos de áudio
│   └── index.html            # Template HTML principal
├── src/
│   ├── components/           # Componentes React
│   ├── context/              # Contextos para estado global
│   ├── utils/                # Utilitários (configuração Firebase)
│   ├── styles/               # Estilos CSS
│   ├── App.js               # Componente principal
│   └── index.js             # Ponto de entrada
├── package.json             # Dependências e scripts
└── README.md               # Este arquivo
```

## 🚀 Instalação e Configuração

### Pré-requisitos

- Node.js (v14 ou superior)
- npm ou yarn

### Passos

1. **Clone o repositório**
   ```bash
   git clone https://github.com/seu-usuario/muxima-do-sul.git
   cd muxima-do-sul
   ```

2. **Instale as dependências**
   ```bash
   npm install
   ```

3. **Configure o Firebase**
   - Crie um projeto no [Firebase Console](https://console.firebase.google.com/)
   - Adicione um aplicativo web
   - Copie as credenciais para `src/utils/firebase.js`
   - Habilite o Firestore Database
   - Configure as regras de segurança

4. **Execute em modo de desenvolvimento**
   ```bash
   npm start
   ```

5. **Abra o navegador**
   Acesse [http://localhost:3000](http://localhost:3000)

## 🏗️ Construindo para Produção

```bash
npm run build
```

Os arquivos otimizados serão gerados na pasta `build/`.

## 🌐 Implantação

### Firebase Hosting

1. Instale a CLI do Firebase
   ```bash
   npm install -g firebase-tools
   ```

2. Faça login
   ```bash
   firebase login
   ```

3. Inicialize o hosting
   ```bash
   firebase init hosting
   ```

4. Implante
   ```bash
   firebase deploy
   ```

### Outras Plataformas

O projeto pode ser implantado em qualquer plataforma de hospedagem estática como:
- Netlify
- Vercel
- GitHub Pages
- Surge.sh

## 📝 Funcionalidades Detalhadas

### Chat Widget com IA

O chat widget oferece três assistentes virtuais especializados:

- **Muxito IA**: Assistente oficial para dúvidas sobre a empresa
- **Ben Ekuikui**: Especialista em comunicação e estratégias de mídia
- **Adilson Chitunda**: Especialista em design gráfico e identidade visual

Cada bot possui respostas automáticas personalizadas e avatares distintos.

### Sistema de Feedback

Os usuários podem:
- Avaliar os serviços com sistema de estrelas (1-5)
- Deixar comentários detalhados
- Visualizar feedbacks de outros usuários

### Painel Administrativo

Acesso restrito (clique 6 vezes no logo para acessar) que permite:
- Gerenciar posts do blog
- Adicionar/Editar itens do portfólio
- Gerenciar podcasts
- Cadastrar parceiros
- Moderar feedbacks

### Multi-idioma

O site oferece suporte completo para:
- Português (PT)
- Inglês (EN)

Com alternância instantânea entre idiomas.

## 🔧 Configuração do Firebase

### Coleções Necessárias

Crie as seguintes coleções no Firestore:

- `posts` - Posts do blog
- `portfolio` - Itens do portfólio
- `podcasts` - Episódios de podcast
- `partners` - Parceiros da empresa
- `feedbacks` - Feedbacks dos usuários
- `contacts` - Mensagens de contato
- `chatMessages` - Mensagens do chat

### Regras de Segurança Recomendadas

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read: if true;
      allow write: if false;
    }
    
    match /feedbacks/{feedbackId} {
      allow create: if true;
      allow update, delete: if request.auth != null;
    }
    
    match /contacts/{contactId} {
      allow create: if true;
    }
    
    match /chatMessages/{messageId} {
      allow create: if true;
    }
  }
}
```

## 🤝 Contribuição

Contribuições são bem-vindas! Por favor, siga estas etapas:

1. Faça um fork do projeto
2. Crie sua branch de feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Copyright (c) [2025] [Muxima do Sul]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


## 🙏 Agradecimentos

- À equipe da Muxima do Sul pela confiança e apoio
- À comunidade React e Firebase pelas ferramentas incríveis
- A todos os clientes e parceiros que inspiram nosso trabalho diário

## 📞 Contato

**Muxima do Sul**  
Endereço: Bairro São João, Rua K, Huambo, Angola  
Telefone: +244 921 672 874  
Email: muximadosul@gmail.com  
Website: [https://www.muximadosul.com](https://www.muximadosul.com)

**Redes Sociais**  
- [Facebook](https://facebook.com/profile.php?id=61569366945646&locale=pt_BR)
- [Instagram](https://www.instagram.com/muxima_do_sul)
- [LinkedIn](https://linkedin.com/company/muxima-do-sul)
- [YouTube](https://www.youtube.com/@muximadosul?sub_confirmation=1)

---

© 2024 Muxima do Sul. Todos os direitos reservados.
