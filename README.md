# Auto Center Veloz — Acompanhamento de Serviços

Web app que dá transparência e agilidade à comunicação entre a oficina **Auto Center Veloz** e seus clientes.
Disciplina de Design Profissional — Estudo de Caso 3.

**Demo (GitHub Pages):** `https://SEU-USUARIO.github.io/autocenter-veloz/`

## 1. Briefing do problema

A Auto Center Veloz (5 elevadores, 6 mecânicos, 2 recepcionistas, sócios Eduardo e Henrique) tem ótima reputação técnica, mas a comunicação é manual:

- o telefone da recepção não para de tocar (clientes querendo saber o status ou ver fotos das peças);
- mecânicos param o serviço para atender a recepção;
- clientes demoram horas para aprovar orçamentos, e o pátio fica lotado de carros parados;
- risco de avaliações negativas online por falha de comunicação.

**Oportunidade:** unir a confiança técnica que a oficina já tem a um canal rápido e transparente de status e aprovação, superando as oficinas informais e igualando o relatório digital das concessionárias, sem o preço delas.

## 2. Solução e justificativa (app × site × sistema)

Escolhi um **web app responsivo** com duas visões:

| Visão | Quem usa | O que faz |
|---|---|---|
| Painel da Oficina | Recepção e mecânicos | Quadro por status, abertura de OS, orçamento por itens, fotos das peças, envio do orçamento |
| Visão do Cliente | Cliente (via link) | Acompanha o status, vê fotos, **aprova ou recusa cada item** com um toque |

**Por que web app e não as outras opções?**

- **App móvel:** exigiria instalação por parte do cliente, que usa a oficina esporadicamente. Isso é uma barreira que reduziria a adesão.
- **Site institucional:** não resolve o problema, pois só divulga a oficina e não resolve status nem aprovação.
- **Sistema/dashboard completo:** útil internamente, mas o cliente não o acessaria. Aqui o painel interno existe, mas o ganho principal está no link que o cliente abre no celular, sem cadastro, a partir de uma mensagem de WhatsApp.

Resultado esperado: menos ligações, aprovação mais rápida, menos tempo de carro parado no pátio.

## 3. Protótipos / telas

Painel da Oficina:

![Painel da Oficina](docs/painel-oficina.png)

Visão do Cliente:

![Visão do Cliente](docs/visao-cliente.png)

## 4. Arquitetura

- **HTML + CSS + JavaScript puro**, em um único arquivo (`index.html`), sem build e sem dependências.
- **Estado:** lista de ordens de serviço no `localStorage` do navegador (protótipo). Cada OS tem cliente, veículo, status, itens do orçamento (aprovado/recusado/pendente), fotos e histórico.
- **Fotos:** redimensionadas no navegador (canvas) antes de salvar.
- **Segurança:** textos digitados são escapados antes de ir para a tela (prevenção de XSS). O repositório não contém credenciais, tokens ou chaves de API.

### Limitações e próximos passos

No protótipo, o painel e a visão do cliente compartilham o mesmo navegador. Em produção, seriam necessários: backend com banco de dados, link único por OS enviado por WhatsApp/SMS, login para a equipe e notificações automáticas.

## 5. Como executar

Não precisa instalar nada.

```bash
git clone https://github.com/SEU-USUARIO/autocenter-veloz.git
cd autocenter-veloz
# abra o index.html no navegador
```

Para publicar: **Settings → Pages → Deploy from a branch → main / (root)**.

## 6. Estrutura

```
autocenter-veloz/
├── index.html
├── docs/            # prints das telas
├── README.md
├── LICENSE          # MIT
└── .gitignore
```

## Licença

[MIT](LICENSE) © 2026 Joaquim
