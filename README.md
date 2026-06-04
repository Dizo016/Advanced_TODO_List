## Preview

<img width="1166" height="833" alt="image" src="https://github.com/user-attachments/assets/0e4c9eb8-e1aa-4e98-b1be-9cdd100d87dc" />

---

# Todo Avançado

Aplicação de lista de tarefas (To-Do List) desenvolvida com HTML, CSS e JavaScript puro, sem dependência de frameworks ou ferramentas de build. As tarefas são persistidas no navegador via **LocalStorage**, garantindo que os dados não sejam perdidos ao recarregar a página.

---

## Funcionalidades

- **Adicionar tarefa** — digite no campo de texto e clique no botão `+` (ou pressione Enter)
- **Concluir tarefa** — clique no ícone de check para marcar/desmarcar uma tarefa como feita
- **Editar tarefa** — clique no ícone de lápis para abrir o formulário de edição; cancele com o botão "Cancelar"
- **Remover tarefa** — clique no ícone `X` para deletar a tarefa
- **Pesquisar** — filtra as tarefas visíveis em tempo real conforme você digita; limpe a busca com o botão de apagar
- **Filtrar por status** — selecione entre *Todos*, *Feitos* ou *A fazer*
- **Persistência** — todas as operações (criar, editar, concluir, remover) são sincronizadas com o `localStorage`

---

## Estrutura do projeto

```
todo_list/
├── index.html        # Estrutura da página
├── css/
│   └── styles.css    # Estilos da aplicação
└── js/
    └── scripts.js    # Lógica e manipulação do DOM
```

---

## Tecnologias utilizadas

| Tecnologia | Uso |
|---|---|
| HTML5 | Estrutura semântica da página |
| CSS3 | Estilização, animações e responsividade |
| JavaScript (ES6+) | Lógica de negócio e manipulação do DOM |
| [Font Awesome 7](https://fontawesome.com/) | Ícones dos botões |
| [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) | Tipografia |
| LocalStorage API | Persistência de dados no navegador |

---

## Como usar

A aplicação está disponível online via GitHub Pages — nenhuma instalação necessária:

**[https://dizo016.github.io/Advanced_TODO_List/](https://dizo016.github.io/Advanced_TODO_List/)**

> As tarefas ficam salvas no `localStorage` do seu navegador, individualmente por dispositivo e navegador.

---

### Instalação local (opcional)

Caso prefira rodar localmente, não é necessário instalar dependências ou rodar um servidor:

```bash
# Clone o repositório
git clone https://github.com/dizo016/Advanced_TODO_List.git

# Acesse a pasta
cd Advanced_TODO_List

# Abra no navegador
# Linux
xdg-open index.html

# macOS
open index.html

# Windows
start index.html
```

Ou simplesmente arraste o arquivo `index.html` para uma aba do seu navegador.

---

### Funcionalidades

1. **Adicionar** — digite sua tarefa no campo principal e pressione Enter ou clique em `+`
2. **Concluir** — clique no botão de check (✔) ao lado da tarefa; ela ficará verde com o texto riscado
3. **Editar** — clique no botão de lápis (✏), altere o texto no formulário de edição e confirme com o botão de check duplo
4. **Remover** — clique no botão `✕` para excluir permanentemente a tarefa
5. **Pesquisar** — use o campo "Pesquisar" na barra de ferramentas para filtrar tarefas por texto
6. **Filtrar** — use o seletor "Filtrar" para exibir *Todos*, apenas os *Feitos* ou apenas os *A fazer*

---

## Detalhes técnicos

### LocalStorage

Os dados são armazenados em formato JSON sob a chave `"todos"`. Cada item tem a estrutura:

```json
{
  "text": "Texto da tarefa",
  "done": false
}
```

### Funções principais (`js/scripts.js`)

| Função | Descrição |
|---|---|
| `saveTodo(text, done, save)` | Cria e insere um item de tarefa no DOM |
| `updateTodo(text)` | Atualiza o texto de uma tarefa existente |
| `toggleForms()` | Alterna a visibilidade entre o formulário de adição e o de edição |
| `getSearchTodos(search)` | Filtra visualmente as tarefas pelo texto de busca |
| `filterTodos(filterValue)` | Exibe tarefas conforme o filtro selecionado (`all`, `done`, `todo`) |
| `loadTodos()` | Carrega as tarefas salvas no `localStorage` ao iniciar a página |
| `saveTodoLocalStorage(todo)` | Persiste uma nova tarefa no `localStorage` |
| `removeTodoLocalStorage(text)` | Remove uma tarefa do `localStorage` pelo texto |
| `updateTodosStautsLocalStorage(text)` | Alterna o status `done` de uma tarefa no `localStorage` |
| `updateTodoLocalStorage(oldText, newText)` | Atualiza o texto de uma tarefa no `localStorage` |

---

## Visual

- **Fundo** — cinza claro `#f4f0f0`
- **Container** — branco com sombra e bordas arredondadas, centralizado e com largura máxima de 450px
- **Tarefa concluída** — fundo verde `#4e895f`, texto branco riscado em itálico
- **Botões** — tema claro com hover escuro (`#102f5e`)

---

## Aprendizados aplicados

Este projeto foi desenvolvido como parte de um curso de Frontend e consolida os seguintes conceitos:

- Manipulação do DOM com JavaScript puro
- Eventos (`submit`, `click`, `keyup`, `change`)
- Delegação de eventos
- API de `localStorage` para persistência de dados
- Organização de código em funções reutilizáveis
- Estilização com CSS puro (Flexbox, transições, classes dinâmicas)
