---
{"dg-publish":true,"permalink":"/scripts/baixar-aditamentos/","dgPassFrontmatter":true,"noteIcon":"","created":"2025-05-16T16:42:20.502-03:00","updated":"2026-05-15T16:52:48.218-03:00","dg-note-properties":{}}
---


``` javascript
// Seleciona todos os botões de aditamento que já existem na página
const botoes = document.querySelectorAll('a.download-adt');

console.log(`🚀 SucemNet Auto-Download: ${botoes.length} arquivos encontrados.`);

botoes.forEach((botao, index) => {
    setTimeout(() => {
        console.log(`[${index + 1}/${botoes.length}] Abrindo aditamento: ${botao.innerText.trim()}...`);
        
        // Dispara o evento de clique no botão real da página
        botao.click();

        if (index === botoes.length - 1) {
            console.log("✅ Processo concluído!");
        }
    }, index * 5000); // Mantém o intervalo de 5 segundos para evitar bloqueios
});
```

``` javascript
const links = Array.from(document.querySelectorAll('a'))
    .filter(link => link.textContent.includes('Abrir Aditamento'));

console.log(`Encontrados ${links.length} links. Iniciando abertura...`);

links.forEach((link, index) => {
    setTimeout(() => {
        // Criamos um elemento temporário para garantir o disparo do download
        const a = document.createElement('a');
        a.href = link.href;
        a.target = '_blank'; // Abre em nova aba para não matar a página atual
        a.rel = 'noopener noreferrer';
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        
        console.log(`[${index + 1}/${links.length}] Abrindo: ${link.href}`);
    }, index * 3000); // 3 segundos entre cada um para não travar o navegador
});
```
