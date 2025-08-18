---
{"dg-publish":true,"permalink":"/scripts/baixar-aditamentos/","dgPassFrontmatter":true,"noteIcon":"","created":"2025-05-16T16:42:20.502-03:00","updated":"2025-08-18T08:01:23.341-03:00"}
---


``` javascript
// Seleciona todos os links ou elementos com o texto "Abrir Aditamento"  
const aditamentoLinks = Array.from(document.querySelectorAll('a')).filter(link => link.textContent.includes('Abrir Aditamento'));  
  
// Função para clicar em cada link com um pequeno atraso entre os cliques  
aditamentoLinks.forEach((link, index) => {  
setTimeout(() => {  
link.click();  
}, index * 10000); // Ajuste o tempo conforme necessário (5000 ms = 5 segundos entre os cliques)  
});
```
