
Excel


Formatos de word
Elimitar Deer ecaner esatico superior derecnho
Borrar imagenes




document.querySelectorAll('td').forEach(function(e, i) {
    if (e.textContent.trim().length == 0) { // if row is empty
        e.parentNode.removeChild(e);
    }
})


document.querySelectorAll('tr').forEach(function(e, i) {
    if (e.textContent.trim().length == 0) { // if row is empty
        e.parentNode.removeChild(e);
    }
})
