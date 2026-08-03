# AETHER Local Authority Engine

## Status

MVP em planejamento e construção.

## Objetivo inicial

Criar um sistema reutilizável para planejar, produzir, revisar e organizar três postagens semanais para o Perfil da Empresa no Google, fortalecendo a relevância local da empresa.

## Primeiro caso de uso

Sistema Fisio — clínica de fisioterapia ortopédica, prevenção e treinamento localizada no Jaguaré, São Paulo.

## Escopo da primeira versão

- Google Business Profile.
- Três publicações por semana.
- Conteúdo em clusters temáticos.
- Uso de fotos e vídeos reais.
- Textos, chamadas para ação e nomes de arquivos padronizados.
- Cobertura equilibrada de serviços, patologias e regiões.
- Aprovação humana antes da publicação.
- Registro do histórico para evitar repetição.

## Canais futuros

O núcleo será preparado para futura adaptação a Instagram, Facebook, LinkedIn, Blog, YouTube, TikTok, Pinterest, Newsletter e WhatsApp. Esses canais não fazem parte do MVP inicial.

## Princípio do produto

Toda configuração deve ser parametrizável. Nome da empresa, serviços, regiões, identidade visual, CTAs, frequência e regras de comunicação não podem ficar presos ao caso da Sistema Fisio.

## Fluxo inicial

```text
Configuração da empresa
        ↓
Calendário e cluster temático
        ↓
Seleção de mídia
        ↓
Criação da publicação
        ↓
Revisão clínica, SEO e comunicação
        ↓
Aprovação de Jefferson
        ↓
Publicação manual no Google
        ↓
Registro no histórico
```

## Estrutura prevista

```text
projects/aether-local-authority-engine/
├── README.md
├── BRIEFING-SISTEMA-FISIO.md
├── PLANO-MVP.md
├── PIPELINE-GBP.md
├── assets/
├── prompts/
├── templates/
└── historico/
```
