## Heurísticas
- As heurísticas são princípios gerais de design usados para avaliar a qualidade da interface. 

## 1. Visibilidade do Status do Sistema
**O sistema nunca deve deixar o usuário no escuro.** Ele precisa informar o que está acontecendo e onde o usuário está.

* **Exemplo da aula:** O Spotify mostra o que está tocando, qual a próxima música e a barra de progresso. O YouTube destaca na lateral qual vídeo da playlist está sendo exibido.
* **Aplicação Dev:** Loadings, breadcrumbs (caminho de navegação), barras de progresso em uploads.

## 2. Correspondência entre o Sistema e o Mundo Real
O sistema deve falar a linguagem do usuário, usando ícones e termos familiares, não jargões técnicos ("Erro 404" vs "Página não encontrada").

* **Exemplo da aula:** O ícone de **Lixeira** para deletar arquivos e a **Lupa** para buscar. São metáforas do mundo físico trazidas para o digital.
* **Conceito:** Não crie ícones enigmáticos; use o que o cérebro já conhece.

## 3. Controle e Liberdade do Usuário
O usuário erra. O sistema deve oferecer uma "saída de emergência" clara para desfazer ações indesejadas sem frustração.

* **Exemplo da aula:** No Gmail, se você joga um e-mail na lixeira, você consegue entrar lá e mover de volta para a caixa de entrada.
* **Aplicação Dev:** Botões de "Desfazer" (Undo), "Cancelar" em formulários e facilidade para voltar à tela anterior.

## 4. Consistência e Padronização
O usuário não deve ter que se perguntar se palavras, situações ou ações diferentes significam a mesma coisa.

* **Exemplo da aula:** Não misture estilos de ícones (um preenchido, um vazado, um colorido). Use famílias de ícones consistentes.
* **Ferramenta:** É aqui que entram os **Style Guides** (Guias de Estilo). Se o botão "Salvar" é verde na página A, ele deve ser verde na página B.

## 5. Prevenção de Erros
Melhor do que uma boa mensagem de erro é um design cuidadoso que evita que o problema ocorra.

* **Exemplo da aula:**
* **Confirmação:** Ao clicar em deletar, o sistema pergunta: "Tem certeza?".
* **Autocomplete do Google:** Previne que você digite a palavra errada, sugerindo a correção ("Você quis dizer...") ou completando a frase.

## 6. Reconhecimento em vez de Memorização
Minimize a carga de memória do usuário tornando objetos, ações e opções visíveis. O usuário não deve ter que lembrar de informações de uma parte do diálogo para outra.

* **Exemplo da aula:** O rótulo (label) do campo de formulário deve ficar visível. Se você clica no campo "Nome" e a palavra "Nome" some, e você se distrai, ao voltar você não lembra mais o que deveria digitar ali.

## 7. Eficiência e Flexibilidade de Uso
O sistema deve atender tanto usuários novatos quanto experientes (Power Users).

* **Exemplo da aula:** Atalhos de teclado universais (`Ctrl+C`, `Ctrl+V`).
* **Insight:** Ferramentas como Figma usam atalhos similares aos do Photoshop. Isso reduz a curva de aprendizado porque aproveita o conhecimento prévio do usuário.

## 8. Estética e Design Minimalista
Não é sobre deixar "bonito", é sobre sinal versus ruído. Cada informação extra na interface compete com as unidades de informação relevantes.

* **Conceito:** "Menos é Mais". Interfaces limpas (como as da Apple) facilitam a tomada de decisão. Evite poluição visual que distraia o usuário do objetivo principal.

## 9. Recuperação Diante de Erros
Quando o erro acontece (e a prevenção falhou), a mensagem deve ser expressa em linguagem simples (sem códigos), indicando o problema e sugerindo uma solução construtiva.

* **Exemplo da aula:** Em um login, se o e-mail já existe, não mostre apenas uma borda vermelha. Diga: "Este e-mail já está cadastrado. Deseja recuperar a senha?".
* **Aplicação Dev:** Tratar exceções no código (`try/catch`) para retornar mensagens amigáveis no front-end, e não o stack trace do erro.

## 10. Ajuda e Documentação
Mesmo que o sistema seja intuitivo, pode ser necessário fornecer ajuda.

* **Exemplo da aula:** O ícone de interrogação `?` no Figma, FAQs, Chatbots ou Tooltips (aquelas dicas que aparecem quando passa o mouse). A ajuda deve ser fácil de encontrar.

---
