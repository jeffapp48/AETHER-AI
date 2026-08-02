# Plano de Implantação — Fase 1

**Projeto:** Visibilidade da Sistema Fisio em buscadores e assistentes de IA  
**Data:** 02/08/2026  
**Objetivo:** Corrigir os sinais essenciais de identidade, localização e rastreamento antes da produção de novos conteúdos.

## Resultado esperado desta fase

Ao final, Google, Bing e mecanismos de IA deverão encontrar informações consistentes sobre:

- nome da clínica;
- endereço e bairro;
- telefone e WhatsApp;
- serviços;
- política de atendimento particular e reembolso;
- programas de 5 ou 10 atendimentos;
- profissionais responsáveis;
- localização próxima ao Terminal Vila Yara e Shopping Continental.

## Etapa 1 — Correções imediatas no site

### Dados que devem aparecer iguais em todo o site

- **Nome:** Sistema Fisio;
- **Telefone/WhatsApp:** (11) 96199-5757;
- **Endereço:** Av. General Mac Arthur, 1738;
- **Bairro:** Vila Lageado;
- **Cidade:** São Paulo/SP;
- **CEP:** 05338-001;
- **Referência:** próximo ao Terminal Vila Yara e Shopping Continental.

### Texto oficial sobre convênios

> O atendimento é particular. A Sistema Fisio fornece a documentação necessária para que o paciente solicite reembolso ao plano de saúde, conforme as regras do contrato dele.

### Texto oficial sobre programas de tratamento

> Os programas de tratamento podem ser de 5 ou 10 atendimentos. A indicação é feita pelo fisioterapeuta responsável durante a consulta diagnóstica, após avaliação clínica individual.

### Páginas a revisar primeiro

1. Home;
2. Fisioterapia;
3. Contato;
4. Sobre ou equipe;
5. Rodapé;
6. Landing pages;
7. Política de convênios e reembolso;
8. Links e botões do WhatsApp.

## Etapa 2 — Instalação do Schema

Arquivo preparado:

`SCHEMA-LOCALBUSINESS-SISTEMA-FISIO.json`

### Antes da instalação, completar

- URL oficial do logotipo;
- URL de imagem principal da clínica;
- horários de funcionamento;
- coordenadas de latitude e longitude;
- links oficiais de Instagram, Facebook, LinkedIn e Google Perfil da Empresa;
- nomes e registros dos fisioterapeutas.

### Local de instalação sugerido

No WordPress, inserir o JSON-LD no cabeçalho da página inicial por uma destas opções:

1. plugin de SEO que aceite Schema personalizado;
2. plugin de inserção de código no cabeçalho;
3. implementação pelo tema filho;
4. Google Tag Manager somente se não houver alternativa mais direta.

Não instalar o mesmo Schema por dois plugins diferentes, para evitar duplicação.

## Etapa 3 — Verificação do robots.txt

O arquivo `robots.txt` deve permitir o acesso aos mecanismos de busca e aos sistemas de busca usados por assistentes de IA.

Modelo inicial:

```txt
User-agent: Googlebot
Allow: /

User-agent: Bingbot
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: ChatGPT-User
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: *
Allow: /

Sitemap: https://www.sistemafisio.com/sitemap_index.xml
```

### Cuidados

- Confirmar a URL real do sitemap antes da publicação;
- Não substituir regras importantes do WordPress sem revisão;
- Verificar se Cloudflare, firewall ou hospedagem bloqueiam os robôs;
- Não confundir `OAI-SearchBot`, usado em busca, com robôs destinados ao treinamento de modelos.

## Etapa 4 — Ferramentas de indexação

Configurar ou revisar:

- Google Search Console;
- Bing Webmaster Tools;
- sitemap XML;
- IndexNow;
- inspeção das páginas principais;
- erros 404 e redirecionamentos;
- versão HTTPS e domínio canônico.

## Etapa 5 — Padronização dos perfis externos

Corrigir, nesta ordem:

1. Google Perfil da Empresa;
2. Bing Places;
3. Apple Business Connect;
4. Instagram;
5. Facebook;
6. LinkedIn;
7. Fresha e plataformas de agendamento;
8. Guia Fácil e demais diretórios.

### Regra principal

Nome, endereço, telefone e site devem ser iguais em todos os perfis.

## Etapa 6 — Autoridade profissional

Criar uma página individual para cada profissional contendo:

- nome completo;
- fotografia real;
- número do CREFITO;
- formação;
- especializações;
- tempo de experiência;
- áreas de atuação;
- serviços realizados;
- artigos publicados ou revisados.

Nos artigos de saúde, mostrar:

- autor;
- revisor clínico, quando aplicável;
- data de publicação;
- data de revisão;
- referências utilizadas.

## Etapa 7 — Páginas prioritárias

Após a correção técnica, produzir ou aprimorar:

1. Fisioterapia ortopédica na Vila Lageado;
2. Fisioterapia no Jaguaré;
3. Fisioterapia próxima à Vila Yara;
4. Fisioterapia próxima ao Shopping Continental;
5. Fisioterapia para idosos;
6. Reabilitação pós-operatória;
7. Fisioterapia para dor no joelho;
8. Fisioterapia para dor lombar;
9. Pilates para idosos;
10. Reembolso de fisioterapia pelo plano de saúde.

## Ordem prática de execução

### Fazer agora

1. Conferir telefone em todas as páginas;
2. Conferir CEP e bairro;
3. Corrigir botões de WhatsApp;
4. Padronizar os textos sobre reembolso e programas;
5. Confirmar horários oficiais;
6. Reunir links das redes e do Google Perfil da Empresa.

### Fazer depois

1. Completar e instalar o Schema;
2. revisar `robots.txt` e sitemap;
3. configurar Bing e IndexNow;
4. corrigir perfis externos;
5. criar páginas locais;
6. iniciar monitoramento mensal das respostas das IAs.

## Critério de conclusão da Fase 1

A fase estará concluída quando:

- nenhuma página apresentar telefone divergente;
- nenhuma página apresentar CEP ou bairro divergente;
- todos os botões abrirem o WhatsApp correto;
- site e perfis usarem o mesmo texto sobre reembolso;
- programas de 5 ou 10 atendimentos estiverem explicados corretamente;
- Schema estiver validado e instalado;
- sitemap estiver acessível;
- os principais robôs não estiverem bloqueados;
- Google e Bing reconhecerem a página principal sem erros críticos.

## Próxima ação do usuário

Fornecer ou confirmar:

- horários oficiais de funcionamento;
- telefone fixo, caso ainda seja utilizado;
- URLs oficiais das redes sociais;
- URL do Google Perfil da Empresa;
- nomes completos, CREFITO e especializações dos profissionais.

Com esses dados, a versão final do Schema e das descrições públicas poderá ser preparada sem campos pendentes.