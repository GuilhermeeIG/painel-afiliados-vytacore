<h1 align="center">🏆 Painel de Afiliados VYTACore</h1>
<p align="center"><b>Gamificação de afiliados integrada às APIs oficiais da Shopee e do TikTok Shop</b></p>

<p align="center">
<img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" /> <img src="https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white" /> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" /> <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=white" /> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" /> <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</p>

> 🔒 O código-fonte deste projeto é **privado**. Este repositório é uma vitrine com a visão geral, a arquitetura e a stack. Quer saber mais? Fale comigo pelo [LinkedIn](https://www.linkedin.com/in/luiz-guilherme-dos-santos-820a792a4/).

## 🎯 O que é

Sistema **em produção** que transforma as vendas dos afiliados em pontos, níveis, ranking e recompensas. A regra central: registro manual nunca gera ponto nem dinheiro. A venda precisa ser confirmada pela API oficial da plataforma, validada pelo backend, aprovada por um administrador e registrada em auditoria.

## ✨ Destaques

- 🔗 **Integração com a Shopee Open Platform**: OAuth da loja, assinatura HMAC-SHA256 e relatório de conversões de afiliados
- 🎵 **Integração com o TikTok Shop**: pedidos por criador pela API de afiliados
- ⏱️ **Sincronização automática** a cada 30 minutos com o Laravel Scheduler
- 🥇 **Ranking, níveis e campanhas** com aprovação administrativa e trilha de auditoria
- 🔌 **API para CRM externo**: somente leitura, paginada e com pull incremental
- 🔐 **Auth por token** (Sanctum), papéis e status de usuário, isolamento de dados por afiliado
- 📚 **Documentação técnica** completa para continuidade do projeto

## 🏗️ Arquitetura

```
 SPA React (TanStack Router) ──Bearer token──▶ API Laravel ──▶ MySQL 8
                                                  │
                    Shopee Open Platform ◀────────┤  (OAuth + HMAC)
                    TikTok Shop API      ◀────────┤
                    CRM externo ─────────────────▶┘  (X-CRM-Key, leitura)
```

## 🛠️ Stack

- **Backend:** PHP 8.4 · Laravel 13 · Sanctum · MySQL 8 · PHPUnit · Pint
- **Frontend:** React 19 · TanStack Router · Vite · Tailwind CSS v4 · shadcn/ui · Vitest
- **Infra:** Docker (desenvolvimento) · Hostinger · Cron + Laravel Scheduler
