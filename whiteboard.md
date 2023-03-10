memoria ram tem varias celulas que ficam uma do lado da outra

NOTAÇÃO BIG 0: PIOR CASO -------- (OMEGA = MINIMO/THETA = MEDIA)
complexidade O de n²: complexidade alta porque aumenta de maneira quadratica o tempo de execução conforma aumenta a entrada

complexidade O de n:complexidade baixa porque aumenta de maneira linear o tempo de execução conforme aumenta a entrada

complexidade O de n + m: linear;
complexidade O de n * m: quadratica;

complexidade O de 1: complexidade constante porque independente da entrada o tempo de execução vai ser a mesma = const arr = arr[0] + arr[1];
complexidade O log de n: complexidade logaritmica, mais baixa que a linear

loop visivel(On): forEach, map, reduce, filter..
loop implicito(On): indexOf, includes, replace, find /// mexem com a estrutura do array => shift, unshift, slice...
nenhum impacto(O1): push, pop, vec[i]

conplexidade de espaço


HASHTABLE

hastable deixa o codigo mais perfomatico:

function twoNumberSum(list, num){  // função de soma e ve se é igual o alvo               
    let hashtable = {}                                
    for(let i = 0; i < list.length; i++){        
        hashtable[list[i]] = true;                      
    }

    for(let i = 0; i < list.length; i++){        
        let diff = num - list[i]                       
        if(diff == num) {
            continue; 
        }
        if(hashtable[diff]) {
            return true; 
        }
    }
    return false;                                
}
-------------------------------------------------
function containsDuplicates(arr) { // ver se tem algum repetido e retornar true
    let arrayElements = {};
    for (let idx = 0; idx < arr.length; idx++) {
    if (arrayElements[arr[idx]] === true){
        return true;
    } 
    arrayElements[arr[idx]] = true;
    }
    return false;
}

----------------------------------------------------------------
function countMostDuplicated(list){ // ver o elemento que mais aparece no array
    const hashtable = {};

    for(let i = 0; i < list.length; i++){
    const valor = list[i];
    
    if(hastable[valor]) === undefined{
        hashtable[valor] = 1 
    } else {
        hashtable[valor]++
    }
    }	
    
    let contagemMaxima = 0;
    let resposta = -1;
    
    for(let i = 0; i < list.length; i++){
    const valor = list[i]
    const contagem = hashtable[valor]
    
    if(contagem > contagemMaxima){
        contagemMaxima = contagem
        resposta = valor
    }         
    }
    
    return resposta;
}
    
    BUSCA BINARIA (const ordem = lst.sort( (a , b) => a - b);)
    
                                            function findIndexInverted(wordList, word){ // achar uma palavra 
                                              let left = 0;
                                              let right = wordList.length - 1;

                                              while(left <= right){
                                                const middle = Math.floor((left + right) / 2);
                                                const element = wordList[middle];

                                                if(word === element){
                                                  return middle;
                                                }

                                                if(word > element){
                                                  right = middle - 1;
                                                } else {
                                                  left = middle + 1;
                                                }
                                              }

                                              return -1;
                                            }
                                            
                                            ------------------------------------------
                                            function findFirstIndex(lst, target){ // numeros repetidos retorna p primeiro
                                              let left = 0;
                                              let right = lst.length - 1;
                                              let first = -1;

                                              while(left <= right){
                                                const middle = Math.floor((left + right) / 2);
                                                let element = lst[middle];

                                                if(element === target){ // se for igual
                                                  first = middle; //a variavel ganha o indice do meio 
                                                  right = middle -1 // e move o meio um antes do novo meio
                                                } else if(element < target){
                                                  left = middle + 1;
                                                } else {
                                                  right = middle - 1;
                                                }
                                              }
                                              return first;
                                            }
                                            ------------------------------------------------------
                                            function lowerbound(list, target){ // retornar cm da regua
                                              let left = 0;
                                              let right = list.length - 1;
                                              let cm = -1;

                                              while(left <= right){
                                                const middle = Math.floor((left + right) / 2);
                                                let element = list[middle];

                                                if(target === element){
                                                  return element;

                                                } else if(target > element){
                                                  cm = element
                                                  left = middle + 1;
                                                } else {
                                                  right = middle - 1;
                                                }
                                              }

                                              return cm
                                            }
                                
                                