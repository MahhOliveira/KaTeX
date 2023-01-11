# KaTeX
KaTeX
npm semantic-release CI codecov Discussions jsDelivr katex.min.js size Gitpod ready-to-code Financial Contributors on Open Collective

O KaTeX é uma biblioteca JavaScript rápida e fácil de usar para renderização matemática TeX na Web.

Rápido: O KaTeX renderiza sua matemática de forma síncrona e não precisa refluir a página. Veja como ele se compara a um concorrente neste teste de velocidade.
Qualidade de impressão: O layout do KaTeX é baseado no TeX de Donald Knuth, o padrão ouro para a composição matemática.
Independente: O KaTeX não tem dependências e pode ser facilmente empacotado com os recursos do seu site.
Renderização do lado do servidor: O KaTeX produz a mesma saída, independentemente do navegador ou do ambiente, para que você possa pré-renderizar expressões usando Node.js e enviá-las como HTML simples.
O KaTeX é compatível com todos os principais navegadores, incluindo Chrome, Safari, Firefox, Opera, Edge e IE 11.

KaTeX suporta grande parte (mas não todos) de LaTeX e muitos pacotes LaTeX. Consulte a lista de funções suportadas.

Experimente o KaTeX na página de demonstração!

Primeiros passos
Modelo inicial
<!DOCTYPE html>
<!-- KaTeX requires the use of the HTML5 doctype. Without it, KaTeX may not render properly -->
<html>
  <head>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.4/dist/katex.min.css" integrity="sha384-vKruj+a13U8yHIkAyGgK1J3ArTLzrFGBbBc0tDp4ad/EyewESeXE/Iv67Aj8gKZ0" crossorigin="anonymous">

    <!-- The loading of KaTeX is deferred to speed up page rendering -->
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.4/dist/katex.min.js" integrity="sha384-PwRUT/YqbnEjkZO0zZxNqcxACrXe+j766U2amXcgMg5457rve2Y7I6ZJSm2A0mS4" crossorigin="anonymous"></script>

    <!-- To automatically render math in text elements, include the auto-render extension: -->
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.4/dist/contrib/auto-render.min.js" integrity="sha384-+VBxd3r6XgURycqtZ117nYw44OOcIax56Z4dCRWbxyPt0Koah1uHoK0o4+/RRE05" crossorigin="anonymous"
        onload="renderMathInElement(document.body);"></script>
  </head>
  ...
</html>
Você também pode baixar o KaTeX e hospedá-lo você mesmo.

Para obter detalhes sobre como configurar a extensão de renderização automática, consulte a documentação.

API
Chamada para renderizar uma expressão TeX diretamente em um elemento DOM. Por exemplo:katex.render

katex.render("c = \\pm\\sqrt{a^2 + b^2}", element, {
    throwOnError: false
});
Chamada para gerar uma cadeia de caracteres HTML da matemática renderizada, por exemplo, para renderização do lado do servidor. Por exemplo:katex.renderToString

var html = katex.renderToString("c = \\pm\\sqrt{a^2 + b^2}", {
    throwOnError: false
});
// '<span class="katex">...</span>'
Certifique-se de incluir os arquivos CSS e de fonte em ambos os casos. Se você estiver fazendo toda a renderização no servidor, não há necessidade de incluir o JavaScript no cliente.

Os exemplos acima usam a opção, que torna inválido entradas como o código-fonte TeX em vermelho (por padrão), com a mensagem de erro como passe o mouse sobre o texto. Para obter outras opções disponíveis, consulte a documentação da API, a documentação de opções e a documentação de manipulação de erros.throwOnError: false
