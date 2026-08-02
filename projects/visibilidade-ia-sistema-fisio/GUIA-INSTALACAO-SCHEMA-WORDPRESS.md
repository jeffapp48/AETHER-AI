# Guia simples — Instalação do Schema da Sistema Fisio no WordPress

**Público:** usuário iniciante em WordPress  
**Objetivo:** instalar o Schema da Sistema Fisio sem editar arquivos do tema  
**Método recomendado:** plugin WPCode  
**Arquivo do Schema:** `SCHEMA-LOCALBUSINESS-SISTEMA-FISIO.json`

---

## Antes de começar

Você precisará de:

- acesso de administrador ao WordPress;
- o arquivo `SCHEMA-LOCALBUSINESS-SISTEMA-FISIO.json` aberto em outra aba;
- aproximadamente 15 minutos;
- uma cópia de segurança recente do site, se sua hospedagem oferecer essa opção.

### Regra de segurança

Não altere os arquivos `functions.php`, `header.php` ou outros arquivos do tema. Este guia usa um plugin justamente para evitar esse risco.

---

# Parte 1 — Verificar se já existe um plugin de SEO

No painel do WordPress:

1. Clique em **Plugins**.
2. Clique em **Plugins instalados**.
3. Procure por algum destes nomes:
   - Rank Math SEO;
   - Yoast SEO;
   - All in One SEO;
   - WPCode.

Anote quais deles estão ativos.

## Importante

Plugins de SEO normalmente já criam parte do Schema do site. Isso não impede a instalação, mas precisamos evitar cadastrar a mesma clínica duas vezes.

O método recomendado neste guia adicionará apenas um bloco principal da empresa, com os dados oficiais da Sistema Fisio.

---

# Parte 2 — Instalar o WPCode

O WPCode permite inserir o código sem mexer nos arquivos do tema.

1. No menu esquerdo do WordPress, clique em **Plugins**.
2. Clique em **Adicionar novo plugin**.
3. Na caixa de pesquisa, digite:

```text
WPCode
```

4. Procure pelo plugin com nome semelhante a:

```text
WPCode – Insert Headers and Footers + Custom Code Snippets
```

5. Confirme que o autor exibido é **WPCode**.
6. Clique em **Instalar agora**.
7. Após a instalação, clique em **Ativar**.

Depois da ativação, aparecerá no menu esquerdo uma opção chamada **Code Snippets** ou **WPCode**.

---

# Parte 3 — Preparar o código correto

O arquivo do GitHub contém somente o objeto JSON. Para instalar no WordPress, ele precisa ficar entre duas tags de script.

O formato será:

```html
<script type="application/ld+json">
COLE AQUI TODO O CONTEÚDO DO ARQUIVO JSON
</script>
```

## Como preparar

1. Abra o arquivo:

```text
projects/visibilidade-ia-sistema-fisio/SCHEMA-LOCALBUSINESS-SISTEMA-FISIO.json
```

2. Selecione todo o conteúdo, começando no primeiro `{` e terminando no último `}`.
3. Copie.
4. Abra o Bloco de Notas do Windows.
5. Digite a primeira linha:

```html
<script type="application/ld+json">
```

6. Na linha seguinte, cole o JSON.
7. Na última linha, digite:

```html
</script>
```

Não apague aspas, vírgulas, chaves ou colchetes do conteúdo.

---

# Parte 4 — Criar o snippet no WPCode

1. No WordPress, clique em **Code Snippets** ou **WPCode**.
2. Clique em **Add Snippet** ou **Adicionar snippet**.
3. Procure a opção **Add Your Custom Code (New Snippet)**.
4. Clique em **Use Snippet**.
5. No título, escreva:

```text
Schema oficial — Sistema Fisio
```

6. Em **Code Type**, escolha:

```text
HTML Snippet
```

7. Na caixa de código, cole todo o conteúdo preparado na Parte 3, incluindo:

```html
<script type="application/ld+json">
```

no começo e:

```html
</script>
```

no final.

---

# Parte 5 — Configurar onde o código aparecerá

Na mesma tela do WPCode:

1. Localize **Insertion** ou **Inserção**.
2. Selecione **Auto Insert**.
3. Em localização, escolha uma opção equivalente a:

```text
Site Wide Header
```

ou:

```text
Cabeçalho de todo o site
```

4. Não escolha área administrativa.
5. Não escolha somente uma página específica.
6. Não altere prioridade, caso o campo apareça.

O Schema principal da empresa pode aparecer em todo o site, pois descreve a organização responsável pelo domínio.

---

# Parte 6 — Ativar o código

1. No topo da tela, localize o botão ou chave **Inactive**.
2. Mude para **Active**.
3. Clique em **Save Snippet** ou **Salvar snippet**.
4. Aguarde a confirmação de que o snippet foi salvo.

Depois disso, abra a página inicial do site em uma nova aba:

```text
https://www.sistemafisio.com/
```

Atualize a página com:

```text
Ctrl + F5
```

---

# Parte 7 — Confirmar se o código está no site

No Google Chrome:

1. Abra a página inicial da Sistema Fisio.
2. Clique com o botão direito em uma área vazia da página.
3. Clique em **Exibir código-fonte da página**.
4. Pressione:

```text
Ctrl + F
```

5. Pesquise por:

```text
jefferson-garcia-franca
```

ou:

```text
Sistema Fisio
```

Se o código aparecer dentro de uma tag `application/ld+json`, a instalação foi realizada.

### Se não aparecer

- confirme se o snippet está como **Active**;
- limpe o cache do WordPress;
- limpe o cache da hospedagem;
- atualize novamente com `Ctrl + F5`;
- verifique se escolheu **Site Wide Header**.

---

# Parte 8 — Validar no Schema Markup Validator

Essa ferramenta verifica se o JSON-LD está corretamente escrito.

1. Abra o Schema Markup Validator.
2. Escolha a opção para testar uma URL.
3. Digite:

```text
https://www.sistemafisio.com/
```

4. Inicie o teste.
5. Procure pelos itens:
   - `MedicalBusiness`;
   - `LocalBusiness`;
   - `Person`;
   - `Jefferson Garcia França`.

## Como interpretar

- **Erro:** precisa ser corrigido.
- **Aviso:** merece análise, mas nem sempre impede o funcionamento.
- **Nenhum erro:** estrutura aceita pelo Schema.org.

Salve uma captura de tela do resultado.

---

# Parte 9 — Testar no Google

Use o Teste de pesquisa aprimorada do Google.

1. Abra o Teste de pesquisa aprimorada.
2. Escolha **URL**.
3. Digite:

```text
https://www.sistemafisio.com/
```

4. Clique para testar.
5. Aguarde a análise.

## Observação importante

O Google pode reconhecer o código e mesmo assim informar que aquele tipo não gera um resultado visual específico. Isso não significa que o Schema esteja inútil. Ele continua ajudando mecanismos e sistemas a entenderem a empresa.

O Google não garante exibição especial nos resultados, mesmo quando a marcação está correta.

---

# Parte 10 — Verificar duplicação

Ao testar o site, observe se aparecem várias entidades semelhantes com nomes como:

- Sistema Fisio;
- Organization;
- LocalBusiness;
- MedicalBusiness.

Ter um `WebSite`, uma `Organization` e um `MedicalBusiness` conectados não é automaticamente um problema.

O problema é encontrar duas clínicas diferentes com:

- o mesmo nome;
- endereços divergentes;
- telefones divergentes;
- identificadores diferentes e sem conexão.

## Caso use Rank Math

O Rank Math pode gerar automaticamente `WebSite`, `Organization` e dados locais. Não desligue nada antes de testar.

Se os dados automáticos estiverem corretos e duplicarem totalmente o Schema criado, será melhor integrar as informações ao Rank Math ou remover somente a duplicação específica, não o sistema inteiro.

O recurso de importação de JSON-LD e o Custom Schema Builder são recursos do Rank Math, mas algumas funções exigem a versão PRO.

## Caso use Yoast SEO

Mantenha o Schema Framework do Yoast ativado. O Yoast cria um grafo conectado do site. Não recomendamos desativar todo o Schema do Yoast somente para instalar o código da clínica.

Se houver duplicação real, a correção deverá conectar ou ajustar a entidade da empresa, e não eliminar todos os dados estruturados do site.

---

# Parte 11 — Solicitar nova leitura ao Google

Depois que os testes estiverem corretos:

1. Entre no Google Search Console.
2. Selecione a propriedade da Sistema Fisio.
3. Na barra superior, insira:

```text
https://www.sistemafisio.com/
```

4. Clique em **Testar URL publicada**, caso essa opção apareça.
5. Depois, clique em **Solicitar indexação**.

O Google pode levar alguns dias para rastrear e processar novamente a página.

---

# Parte 12 — Checklist final

Marque cada item:

- [ ] Fiz uma cópia de segurança.
- [ ] Verifiquei quais plugins de SEO estão ativos.
- [ ] Instalei e ativei o WPCode.
- [ ] Copiei o JSON completo sem alterar o conteúdo.
- [ ] Coloquei o JSON entre as tags `<script>`.
- [ ] Escolhi o tipo `HTML Snippet`.
- [ ] Configurei `Auto Insert`.
- [ ] Escolhi `Site Wide Header`.
- [ ] Ativei e salvei o snippet.
- [ ] Encontrei o código no código-fonte da página.
- [ ] Testei no Schema Markup Validator.
- [ ] Testei no Google Rich Results Test.
- [ ] Verifiquei possíveis duplicações.
- [ ] Solicitei nova indexação no Search Console.

---

# Como remover rapidamente em caso de problema

Se alguma página apresentar comportamento estranho:

1. Entre no WordPress.
2. Abra **Code Snippets**.
3. Localize:

```text
Schema oficial — Sistema Fisio
```

4. Mude de **Active** para **Inactive**.
5. Salve.
6. Limpe o cache.

Desativar o snippet remove o código sem apagar o restante do site.

---

# O que não fazer

- Não colar o código em uma página visível como texto comum.
- Não editar arquivos do tema diretamente.
- Não instalar o mesmo Schema em dois plugins diferentes.
- Não alterar telefone, endereço, coordenadas ou CREFITO sem atualizar a fonte oficial.
- Não adicionar avaliações ou notas no Schema sem critérios e conteúdo público correspondente.
- Não desativar todo o Schema do Rank Math ou Yoast por conta própria.

---

# Resultado esperado

Depois da instalação, mecanismos de busca e sistemas de IA poderão encontrar uma descrição estruturada e consistente da Sistema Fisio, incluindo:

- nome da clínica;
- endereço e coordenadas;
- telefones;
- horários;
- redes sociais;
- serviços;
- fisioterapeuta responsável;
- registro profissional;
- política de atendimento particular e reembolso.

A instalação correta ajuda na compreensão da empresa, mas não garante posição, recomendação ou exibição especial nos resultados de busca.
