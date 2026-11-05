# Fale Conosco — Faculdade Horizonte

Uma página de contato para uma faculdade fictícia, feita com **HTML, CSS e JavaScript puros** (sem frameworks). O projeto começou como um exercício de front-end para praticar marcação semântica, estilização responsiva e interatividade básica.

🔗 **Demonstração online:** https://eumarllonlrn.github.io/college-contact-form/

## Funcionalidades

- Formulário dividido em duas seções: **Sobre você** e **Sua mensagem**
- Validação nativa do navegador (campos obrigatórios, formato de e-mail, tamanho mínimo)
- Mensagens de erro exibidas só depois que o usuário interage com o campo, ligadas a ele por `aria-describedby` para leitores de tela
- Seletor de perfil em formato de chips (Futuro aluno, Aluno atual etc.)
- Contador de caracteres em tempo real no campo de mensagem
- Máscara automática de telefone no formato brasileiro: `(00) 00000-0000`
- Botão de envio muda para "Enviando…" para evitar envios duplicados
- Página de agradecimento que cumprimenta o usuário pelo nome
- Layout responsivo (adaptado para celular)
- Modo escuro automático que segue o tema do sistema
- Respeita a configuração de acessibilidade "reduzir movimento"

## Tecnologias

| Tecnologia | Usada para |
| --- | --- |
| HTML5 | Estrutura semântica e validação do formulário |
| CSS3 | Variáveis CSS, Grid, Flexbox, `clamp()`, media queries e pseudo-classes |
| JavaScript | Tratamento de eventos, manipulação do DOM e `sessionStorage` |
| Google Fonts | Fraunces (títulos) e Inter (texto) |

## Estrutura do projeto

```
.
├── index.html       # Página com o formulário de contato
├── obrigado.html    # Página exibida após o envio
├── css/
│   └── styles.css   # Todos os estilos
└── js/
    └── main.js      # Contador de caracteres, máscara de telefone e envio
```

## Como executar

Não é preciso instalar nada:

1. Baixe ou clone o repositório
   ```bash
   git clone https://github.com/eumarllonlrn/college-contact-form.git
   ```
2. Abra o `index.html` no navegador

> Dica: no VS Code, a extensão **Live Server** recarrega a página automaticamente a cada alteração.

## O que eu aprendi

### HTML

- Estruturei o formulário com tags **semânticas**: `<main>`, `<form>`, `<fieldset>` e `<legend>` para agrupar campos relacionados.
- Associei cada `<label>` ao seu campo usando `for` e `id`, o que melhora a acessibilidade e permite clicar no texto do rótulo para focar o campo.
- Agrupei os chips de perfil em um `<fieldset>` próprio com `<legend>`, a forma nativa de rotular um grupo de botões de rádio.
- Liguei cada mensagem de erro ao seu campo com `aria-describedby`, para que os leitores de tela a anunciem.
- Usei os tipos de input adequados (`email`, `tel`, `radio`, `checkbox`) e atributos como `required`, `minlength`, `maxlength` e `autocomplete`, para que o próprio navegador valide os dados e ajude o usuário.
- Aprendi a diferença entre usar `<br>` para espaçamento e deixar o espaçamento por conta do CSS.

### CSS

- Organizei cores e tamanhos em **variáveis CSS** (`:root`), para que o tema possa ser alterado editando poucos valores.
- Adicionei **modo escuro** com `prefers-color-scheme`, redefinindo apenas essas variáveis, e desativei as transições com `prefers-reduced-motion`.
- Usei `:is()` para aplicar uma regra a vários seletores e `clamp()` para um título que se ajusta ao tamanho da tela.
- Usei **Grid** para colocar campos lado a lado e **Flexbox** para alinhar rótulos, chips e a caixa de seleção.
- Deixei o layout **responsivo** com `@media`: no celular, os campos ficam em uma única coluna e o botão ocupa toda a largura.
- Estilizei os estados de interação: `:hover`, `:focus-visible`, `:checked` e `:user-invalid`.
- Transformei os botões de rádio em chips escondendo visualmente o input e estilizando o `<span>` ao lado com o combinador `+`.
- **Um bug que me ensinou muito:** esqueci um `;` e uma `}` em uma regra, e todo o CSS abaixo dela parou de funcionar. Aprendi a conferir se as chaves estão bem fechadas e a prestar atenção aos avisos do editor.

### JavaScript

- Dividi o script em funções pequenas e com nomes claros (`formatarTelefone`, `salvarNome`, `recuperarNome`, `configurarFormulario`, `configurarPaginaObrigado`), cada uma com uma única responsabilidade.
- Selecionei elementos com `getElementById` e `form.elements`, e tratei as ações do usuário com `addEventListener`.
- Criei um **contador de caracteres** atualizado no evento `input`.
- Criei uma **máscara de telefone** usando uma expressão regular (`/\D/g`) para manter só os dígitos antes de formatá-los.
- No envio, chamei `evento.preventDefault()`, desativei o botão, guardei o nome no `sessionStorage` e redirecionei para a página definida no `action` do formulário.
- Usei `try/catch` para a página continuar funcionando mesmo que o navegador bloqueie o armazenamento.
- Aprendi a usar **um único arquivo JS em duas páginas**, verificando se cada elemento existe antes de usá-lo.

## Próximos passos

- [ ] Enviar os dados para um back-end real ou serviço de formulários (por exemplo, Formspree)
- [x] Adicionar modo escuro com `prefers-color-scheme`
- [x] Ligar as mensagens de erro aos campos com `aria-describedby`
- [x] Colocar o grupo de chips em um `<fieldset>` próprio
- [ ] Adicionar um botão para alternar manualmente entre tema claro e escuro

## Autor

Feito por **Marllon Lorran** — [LinkedIn](https://www.linkedin.com/in/eumarllonlrn/) · [GitHub](https://github.com/eumarllonlrn)
