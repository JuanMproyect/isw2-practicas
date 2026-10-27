function generarNumeroSecreto(){
    let numeroGenerado = Math.floor(Math.random()*numeroMaximo)+1;

    console.log(numeroGenerado);
    console.log(listaNumerosSorteados);
    //si ya sorteamos todos los numeros
    if(listaNumerosSorteados.length == numeroMaximo){
        asignarTextoElemento('p', 'Ya se sortearon todos los numeros posibles');
    } else { 
    //si el numero generado esta incluido en la lista
    if(listaNumerosSorteados.includes(numeroGenerado)){
        return generarNumeroSecreto();
    } else {
        listaNumerosSorteados.push(numeroGenerado);
        return numeroGenerado;
    }
}
}


function generarNumeroSecreto(maximo, listaSorteados) {
    if (listaSorteados.length >= maximo) {
        return null; 
    }

    let numeroGenerado;
    
    // Usamos un bucle clásico en lugar de recursión para evitar saturar la memoria
    do {
        numeroGenerado = Math.floor(Math.random() * maximo) + 1;
    } while (listaSorteados.includes(numeroGenerado));

    listaSorteados.push(numeroGenerado);
    return numeroGenerado;
}
