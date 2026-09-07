# Smarket

> Visual search + AR try-on + live shopping + AI assistant — em um único marketplace mobile.

**Status atual:** Conceito + arquitetura definida. Repositório em estágio inicial (README + visão).  
**Objetivo do MVP:** Entregar o primeiro pilar (visual search + checkout) funcional antes de expandir.

---

## O que é o Smarket

O Smarket não é um app de headset. É um app mobile (estilo Google Lens) que vira um marketplace completo:

1. Você vê um item na rua, revista ou foto
2. Abre o Smarket e aponta a câmera
3. O app reconhece o item (ou similares) e mostra onde comprar
4. Dentro do mesmo app: reviews, comparação de preços, try-on em AR no seu ambiente
5. Live shopping nativo (sellers transmitindo o produto que você acabou de escanear)
6. Assistente de IA que conversa, recomenda e ajuda a fechar a compra
7. Compra sem sair do app

A monetização prevista: comissão por venda, ads e potencial white-label/SDK para varejistas.

O insight inicial veio do Apple Vision Pro, mas o foco real é **mobile** — onde todo mundo já tem câmera e conexão.

---

## O gap que existe (e por que a ideia ainda é válida)

Nenhuma plataforma dominante une os quatro pilares em um só fluxo de marketplace:

| Pilar                    | O que já existe                                      | Limite atual                                      |
|--------------------------|------------------------------------------------------|---------------------------------------------------|
| Visual search universal  | Google Lens, Pinterest Lens, Amazon StyleSnap        | Redireciona para fora ou fica preso no próprio catálogo |
| AR try-on                | Sephora, Nike, IKEA, WebAR                           | Apps de marca isolados                            |
| Live shopping            | TikTok Shop, Whatnot, Amazon Live, Shopee Live       | Plataformas separadas                             |
| Assistente de IA         | Chatbots e recomendações genéricas                   | Raramente fecha o ciclo de compra no mesmo lugar  |

Google já tem as peças (Lens + Shopping Graph + AR + Ads + YouTube Shopping), mas culturalmente conecta, não fecha a venda em um marketplace próprio. O diferencial do Smarket é a **unificação da experiência**.

Mercados individuais continuam crescendo (visual search, AR commerce e live shopping com CAGRs fortes). A janela de unificação ainda está aberta — mas não por tempo indeterminado.

---

## Arquitetura técnica do MVP (resumo)

**Frontend mobile:** React Native ou Flutter (câmera nativa + WebView para WebAR)  
**Backend:** FastAPI (Python) + PostgreSQL + pgvector + Redis + Celery  
**Visual search:** Cloud Vision / CLIP embeddings + busca por similaridade no pgvector (fallback para APIs externas)  
**AR:** Google Model Viewer / WebAR (8th Wall, Three.js + WebXR)  
**Live:** WebRTC ou RTMP + WebSocket para chat  
**IA:** LLM (GPT-4o-mini / Claude Haiku) + LangChain + RAG  
**Pagamentos:** Stripe ou Mercado Pago (com split de marketplace)  
**Infra:** Docker → Cloud Run / Railway (Kubernetes só em escala)

Custos estimados de MVP: ~US$ 50–100/mês no início.

---

## Roadmap de implementação (recomendado)

Não construir tudo de uma vez. Prioridade absoluta: um pilar forte primeiro.

| Fase | Semanas | Entrega principal                          | Objetivo                          |
|------|---------|--------------------------------------------|-----------------------------------|
| 1    | 1–4     | Visual search básico (foto → resultados)   | Provar matching e UX de discovery |
| 2    | 5–8     | Catálogo de sellers + checkout             | Fechar o ciclo de compra          |
| 3    | 9–12    | AR try-on (Model Viewer / WebAR)           | Aumentar conversão e confiança    |
| 4    | 13–16   | Assistente de IA com RAG                   | Personalização e retenção         |
| 5    | 17–20   | Live shopping (WebRTC + chat)              | Engagement e vendas em tempo real |
| 6    | 21–24   | Polish, testes, deploy e demo em vídeo     | Pronto para tração / pitch        |

**Sugestão de go-to-market inicial:**  
Começar com visual search + checkout. Quando tiver tração e sellers, adicionar AR. Depois live e IA.

Caminhos mais realistas:
- Marketplace independente (B2C) em nicho
- Plataforma white-label / SDK para varejistas (B2B)
- Aquisição por player que quer entrar no espaço (Shopify, varejistas grandes, etc.)

---

## Estado atual do repositório

Este repositório ainda está em estágio de **visão e planejamento**.  
Não há código de produto, protótipo funcional nem demo pública.

O próximo passo de maior valor é transformar esta visão em um MVP mínimo e demonstrável (Fase 1 + 2).

---

## Como contribuir / próximos passos

1. Definir vertical inicial (moda, calçados, casa, etc.)
2. Montar catálogo seed (mesmo que pequeno)
3. Implementar o fluxo de visual search + resultados + checkout
4. Gravar demo em vídeo do fluxo ponta a ponta
5. Iterar com feedback real de usuários e sellers

---

## Contato

Lucas H. M. Vieira  
[lucasmulato369@gmail.com](mailto:lucasmulato369@gmail.com)

---

**A ideia é válida. O gap existe. O diferencial não é tecnologia isolada — é a unificação da experiência. A execução (começando pequeno e bem) decide se vira produto.**
