# Guia de Estilo Front-End

## Convenções CSS
- Use **BEM** para nomes de classes: `.[bloco]__[elemento]--[modificador]`.
- Separe estilos globais e componentes em arquivos distintos.

## Estrutura de Pastas (exemplo)
```
src/
  components/
    Button/
      Button.js
      Button.css
  pages/
    Home/
      Home.js
      Home.css
```

## JavaScript
- Padrões: **ESLint** com regras Airbnb.
- Use **Promises** e **async/await** de forma consistente.
- Nomeie funções de forma descritiva.

## Acessibilidade
- Utilize tags semânticas (`<header>`, `<main>`, `<footer>`).
- Adicione atributos ARIA quando necessário.
- Garanta **contraste** de cores e responsividade.

## Exemplos de Código

### Exemplo de componente React (se aplicável)
```jsx
function Button({ label, onClick }) {
  return (
    <button className="button" onClick={onClick}>
      {label}
    </button>
  );
}
```
