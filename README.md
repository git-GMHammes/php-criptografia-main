# 🔐 PHP Criptografia - Sistema de Segurança de Dados

[![PHP Version](https://img.shields.io/badge/PHP-8.1%2B-blue.svg)](https://www.php.net/)
[![CodeIgniter](https://img.shields.io/badge/CodeIgniter-4.x-orange.svg)](https://codeigniter.com/)
[![React](https://img.shields.io/badge/React-18.x-61dafb.svg)](https://reactjs.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1.svg)](https://www.mysql.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> Sistema completo de criptografia e descriptografia de dados sensíveis antes do armazenamento em banco de dados, garantindo segurança em camadas.

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Arquitetura](#arquitetura)
- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalação)
- [Configuração](#configuração)
- [Uso](#uso)
- [API Endpoints](#api-endpoints)
- [Exemplos de Código](#exemplos-de-código)
- [Pontos de Função](#pontos-de-função)
- [Segurança](#segurança)
- [Contribuindo](#contribuindo)
- [Licença](#licença)
- [Contato](#contato)

## 🎯 Sobre o Projeto

O **PHP Criptografia** é um sistema robusto desenvolvido para proteger dados sensíveis através de criptografia em múltiplas camadas antes do armazenamento no banco de dados. Ideal para aplicações que lidam com informações confidenciais como CPF, RG, dados bancários, senhas e informações pessoais.

### Principais Diferenciais

- 🛡️ **Criptografia AES-256-GCM** - Algoritmo de última geração
- 🔄 **Criptografia bidirecional** - Criptografa e descriptografa conforme necessário
- 🎨 **Interface moderna** - Frontend em ReactJS responsivo
- ⚡ **API RESTful** - Backend escalável com CodeIgniter 4
- 🔐 **Múltiplas camadas de segurança** - Salt, IV e chaves rotativas
- 📊 **Logs de auditoria** - Rastreamento completo de operações

## ✨ Funcionalidades

### Backend (API Rest)
- ✅ Criptografia de dados com AES-256-GCM
- ✅ Descriptografia segura com validação de integridade
- ✅ Gerenciamento de chaves de criptografia
- ✅ Sistema de rotação automática de chaves
- ✅ Logs de auditoria para compliance
- ✅ Validação de dados antes da criptografia
- ✅ API RESTful documentada

### Frontend (ReactJS)
- ✅ Interface intuitiva para teste de criptografia
- ✅ Formulários dinâmicos para entrada de dados
- ✅ Visualização de dados criptografados/descriptografados
- ✅ Dashboard de métricas de segurança
- ✅ Gerenciamento de chaves via interface
- ✅ Tema dark/light mode
- ✅ Totalmente responsivo

### Banco de Dados
- ✅ Estrutura otimizada para dados criptografados
- ✅ Índices de busca sem comprometer segurança
- ✅ Tabelas de auditoria e logs
- ✅ Procedures para operações seguras
- ✅ Backup automático de chaves

## 🚀 Tecnologias Utilizadas

### Backend
```
- PHP 8.1+
- CodeIgniter 4.x
- OpenSSL Extension
- Composer
```

### Frontend
```
- ReactJS 18.x
- Axios (API Client)
- React Router
- Tailwind CSS / Material-UI
- React Hook Form
```

### Banco de Dados
```
- MySQL 8.0+
- InnoDB Engine
```

### Ferramentas de Desenvolvimento
```
- Git & GitHub
- Laragon / Docker
- Postman / Insomnia
- PHPUnit (Testes)
- ESLint (Code Quality)
```

## 🏗️ Arquitetura
```
php-criptografia-main/
│
├── backend/                    # API CodeIgniter
│   ├── app/
│   │   ├── Controllers/
│   │   │   ├── API/
│   │   │   │   ├── CriptografiaController.php
│   │   │   │   └── ChavesController.php
│   │   ├── Models/
│   │   │   ├── CriptografiaModel.php
│   │   │   └── AuditoriaModel.php
│   │   ├── Libraries/
│   │   │   ├── CryptoService.php
│   │   │   └── KeyManager.php
│   │   ├── Config/
│   │   │   ├── Encryption.php
│   │   │   └── Routes.php
│   │   └── Database/
│   │       └── Migrations/
│   ├── public/
│   ├── tests/
│   └── composer.json
│
├── frontend/                   # React Application
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── CryptoForm.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   └── KeyManager.jsx
│   │   ├── services/
│   │   │   └── api.js
│   │   ├── hooks/
│   │   ├── styles/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   └── vite.config.js
│
├── database/                   # Scripts SQL
│   ├── schema.sql
│   ├── migrations/
│   └── seeds/
│
├── docs/                       # Documentação
│   ├── API.md
│   ├── SECURITY.md
│   └── DEPLOYMENT.md
│
├── .env.example
├── .gitignore
├── docker-compose.yml
├── README.md
└── LICENSE
```

## 📦 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- PHP >= 8.1
- Composer
- Node.js >= 18.x
- MySQL >= 8.0
- OpenSSL Extension habilitada
- Git

## 🔧 Instalação

### 1. Clone o repositório
```bash
git clone https://github.com/git-GMHammes/php-criptografia-main.git
cd php-criptografia-main
```

### 2. Configurar Backend
```bash
cd backend

# Instalar dependências
composer install

# Copiar arquivo de configuração
cp .env.example .env

# Configurar variáveis de ambiente no .env
# DB_HOST, DB_NAME, DB_USER, DB_PASS
# ENCRYPTION_KEY (gerar com: php spark key:generate)

# Executar migrations
php spark migrate

# Executar seeders (opcional)
php spark db:seed CriptografiaSeeder
```

### 3. Configurar Frontend
```bash
cd ../frontend

# Instalar dependências
npm install

# Copiar arquivo de configuração
cp .env.example .env

# Configurar variável da API no .env
# VITE_API_URL=http://localhost:8080/api
```

### 4. Configurar Banco de Dados
```bash
# Executar script de schema
mysql -u root -p < database/schema.sql

# Ou importe via phpMyAdmin/Adminer
```

## ⚙️ Configuração

### Backend (.env)
```env
#--------------------------------------------------------------------
# ENVIRONMENT
#--------------------------------------------------------------------
CI_ENVIRONMENT = development

#--------------------------------------------------------------------
# DATABASE
#--------------------------------------------------------------------
database.default.hostname = localhost
database.default.database = php_criptografia
database.default.username = root
database.default.password = 
database.default.DBDriver = MySQLi

#--------------------------------------------------------------------
# ENCRYPTION
#--------------------------------------------------------------------
encryption.key = sua-chave-gerada-aqui-32-chars
encryption.driver = OpenSSL
encryption.cipher = AES-256-GCM

#--------------------------------------------------------------------
# SECURITY
#--------------------------------------------------------------------
security.tokenName = csrf_token
security.headerName = X-CSRF-TOKEN
security.cookieName = csrf_cookie
```

### Frontend (.env)
```env
VITE_API_URL=http://localhost:8080/api
VITE_APP_NAME=PHP Criptografia
VITE_APP_VERSION=1.0.0
```

## 🎮 Uso

### Iniciar Backend
```bash
cd backend
php spark serve
# Servidor rodando em: http://localhost:8080
```

### Iniciar Frontend
```bash
cd frontend
npm run dev
# Aplicação rodando em: http://localhost:5173
```

### Acessar a Aplicação

Abra seu navegador em `http://localhost:5173`

## 🔌 API Endpoints

### Criptografia
```http
POST /api/criptografia/encrypt
Content-Type: application/json

{
  "data": "CPF: 123.456.789-00",
  "field_type": "cpf"
}

Response:
{
  "success": true,
  "encrypted_data": "aGVsbG8gd29ybGQgZW5jcnlwdGVk...",
  "iv": "random_iv_here",
  "hash": "integrity_hash"
}
```
```http
POST /api/criptografia/decrypt
Content-Type: application/json

{
  "encrypted_data": "aGVsbG8gd29ybGQgZW5jcnlwdGVk...",
  "iv": "random_iv_here",
  "hash": "integrity_hash"
}

Response:
{
  "success": true,
  "decrypted_data": "CPF: 123.456.789-00"
}
```

### Gerenciamento de Chaves
```http
GET /api/chaves/list
POST /api/chaves/generate
PUT /api/chaves/rotate
DELETE /api/chaves/:id
```

### Auditoria
```http
GET /api/auditoria/logs
GET /api/auditoria/stats
```

## 💻 Exemplos de Código

### Backend - Criptografar dados
```php
<?php

namespace App\Controllers\API;

use App\Libraries\CryptoService;

class CriptografiaController extends BaseController
{
    protected $cryptoService;
    
    public function __construct()
    {
        $this->cryptoService = new CryptoService();
    }
    
    public function encrypt()
    {
        $data = $this->request->getJSON();
        
        $result = $this->cryptoService->encrypt($data->data);
        
        return $this->response->setJSON([
            'success' => true,
            'encrypted_data' => $result['encrypted'],
            'iv' => $result['iv'],
            'hash' => $result['hash']
        ]);
    }
}
```

### Frontend - Formulário de Criptografia
```jsx
import React, { useState } from 'react';
import { encryptData } from '../services/api';

function CryptoForm() {
  const [inputData, setInputData] = useState('');
  const [encryptedData, setEncryptedData] = useState(null);
  
  const handleEncrypt = async () => {
    try {
      const response = await encryptData({
        data: inputData,
        field_type: 'text'
      });
      setEncryptedData(response.data);
    } catch (error) {
      console.error('Erro ao criptografar:', error);
    }
  };
  
  return (
    <div className="crypto-form">
      <textarea 
        value={inputData}
        onChange={(e) => setInputData(e.target.value)}
        placeholder="Digite os dados para criptografar"
      />
      <button onClick={handleEncrypt}>Criptografar</button>
      
      {encryptedData && (
        <div className="result">
          <p><strong>Dados Criptografados:</strong></p>
          <code>{encryptedData.encrypted_data}</code>
        </div>
      )}
    </div>
  );
}

export default CryptoForm;
```

## 📊 Pontos de Função

### Análise de Pontos de Função (APF)

| Tipo de Função | Quantidade | Complexidade | PF |
|----------------|------------|--------------|-----|
| **Entradas Externas (EI)** |
| Formulário de Criptografia | 1 | Média | 4 |
| Formulário de Descriptografia | 1 | Média | 4 |
| Gerenciamento de Chaves | 3 | Alta | 18 |
| **Saídas Externas (EO)** |
| Relatório de Auditoria | 1 | Alta | 7 |
| Dashboard de Métricas | 1 | Média | 5 |
| **Consultas Externas (EQ)** |
| Listar Dados Criptografados | 1 | Baixa | 3 |
| Buscar Logs | 1 | Média | 4 |
| **Arquivos Lógicos Internos (ILF)** |
| Tabela de Dados Criptografados | 1 | Alta | 15 |
| Tabela de Chaves | 1 | Alta | 15 |
| Tabela de Auditoria | 1 | Média | 10 |
| **Arquivos de Interface Externa (EIF)** |
| API Externa (se houver) | 0 | - | 0 |

**Total de Pontos de Função (Não Ajustados):** 85 PF

**Fator de Ajuste (estimado):** 1.0

**Total de Pontos de Função Ajustados:** 85 PF

### Estimativa de Esforço

- **Produtividade média:** 10 PF/pessoa-dia
- **Esforço estimado:** 8.5 dias-pessoa
- **Prazo estimado (1 desenvolvedor):** ~2 semanas

## 🔒 Segurança

### Boas Práticas Implementadas

- ✅ Criptografia AES-256-GCM (autenticada)
- ✅ Chaves armazenadas fora do repositório (.env)
- ✅ IV (Initialization Vector) aleatório para cada operação
- ✅ Validação de integridade com hash
- ✅ Proteção contra CSRF
- ✅ Sanitização de inputs
- ✅ Prepared Statements (SQL Injection)
- ✅ Rate limiting na API
- ✅ Logs de auditoria completos
- ✅ HTTPS obrigatório em produção

### Recomendações

⚠️ **NUNCA** commite o arquivo `.env` com chaves reais
⚠️ Use HTTPS em produção
⚠️ Implemente rotação periódica de chaves
⚠️ Mantenha backups seguros das chaves
⚠️ Monitore logs de auditoria regularmente

## 🤝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFuncionalidade`)
3. Commit suas mudanças (`git commit -m 'Add: Nova funcionalidade'`)
4. Push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abra um Pull Request

### Padrões de Código

- **PHP:** PSR-12
- **JavaScript:** ESLint + Prettier
- **Commits:** Conventional Commits

## 📄 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

## 📞 Contato

**Gustavo Hammes** - git-GMHammes

- GitHub: [@git-GMHammes](https://github.com/git-GMHammes)
- Website: [habilidade.com](https://habilidade.com)
- Email: contato@habilidade.com

**Link do Projeto:** [https://github.com/git-GMHammes/php-criptografia-main](https://github.com/git-GMHammes/php-criptografia-main)

---

## 📚 Documentação Adicional

- [Documentação da API](docs/API.md)
- [Guia de Segurança](docs/SECURITY.md)
- [Deploy em Produção](docs/DEPLOYMENT.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)

---

<p align="center">
  Desenvolvido com ❤️ por <a href="https://github.com/git-GMHammes">Gustavo Hammes</a>
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/git-GMHammes/php-criptografia-main?style=social" alt="Stars">
  <img src="https://img.shields.io/github/forks/git-GMHammes/php-criptografia-main?style=social" alt="Forks">
  <img src="https://img.shields.io/github/watchers/git-GMHammes/php-criptografia-main?style=social" alt="Watchers">
</p>