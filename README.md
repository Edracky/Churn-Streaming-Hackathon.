# CHURN-STREAMING-HACKATHON

Projeto do hackathon para prever **evasão de clientes (churn)** em um serviço de streaming, usando **Regressão Logística** e **Random Forest** dentro de um pipeline completo de machine learning.

---

## OBJETIVO DO PROJETO

- Identificar clientes com maior probabilidade de cancelar a assinatura.  
- Ajudar o time de negócio com insights de quais variáveis mais influenciam o churn.  
- Entregar um **modelo treinado e salvo** que possa ser consumido por uma API do back-end do hackathon.

---

## DADOS E FEATURES

- Dataset de clientes de um serviço de streaming, contendo:
  - Tempo de assinatura em meses.  
  - Valor mensal pago e tipo de plano.  
  - Comportamento de uso (visualizações no mês, tempo médio de sessão).  
  - Avaliações de conteúdo e da plataforma.  
  - Número de contatos com o suporte.  
  - Método de pagamento, dispositivo principal, formato mais assistido.  
  - Satisfação média, nível de engajamento e rótulo de churn (0 = continua, 1 = churn).

- Durante a limpeza:
  - Removemos a coluna `client_id` (não entra na modelagem).  
  - Passamos a usar apenas o **índice do DataFrame** como identificador interno de cada cliente.
 
- Criamos algumas features de negócio:
  - `valor_por_hora`: relação entre valor mensal e tempo total assistido (proxy de custo-benefício).  
  - `alto_atrito`: indicador binário para clientes com muitos contatos de suporte.  
  - `satisfacao_media`: média de diferentes notas de avaliação (conteúdo/plataforma).

- Conjunto final de features usadas pelo modelo (`features_core_ext`):

```python
features_core_ext = [
    'tempo_assinatura_meses',
    'valor_mensal',
    'plano_assinatura',
    'visualizacoes_mes',
    'tempo_medio_sessao_min',
    'avaliacao_conteudo',
    'media_avaliacao_plataforma',
    'contatos_suporte',
    'metodo_pagamento',
    'formato_mais_assistido',
    'dispositivo_principal',
    'faixa_tempo_assinatura',
    'valor_por_hora',
    'engajamento_nivel',
    'satisfacao_media',
    'alto_atrito'
]
