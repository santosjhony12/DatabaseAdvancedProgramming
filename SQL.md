# Programação Avançada em Banco de Dados
PLSQL - Procedural Language + SQL - Linguagem nativa do Oracle interpretada
Roda direto no servidor
Código fonte fica armazenado no servidor.
Também pode ser executado em modo de script
Não é Orientado a Objetos
Conseguimos fazer debug

- Procedure
- Função 
- Package 
- View


## Estrutura básica

### BLOCO ANONIMO - NÃO EXISTE COMO OBJETO NO BANCO

```
DECLARE
	<TODAS AS VARIAVEIS DO PROGRAMA>
BEGIN
	<CODIGO>
EXCEPTION
	<TRATAMENTO>
END;
```


### BLOCO NOMEADO - OBJETO EXISTENTE NO BANCO

```
CREATE [PROCEDURE | FUNCTION] <nome> is
	<TODAS AS VARIAVEIS DO PROGRAMA>
BEGIN
	<CODIGO>
EXCEPTION
	<TRATAMENTO>
END;
```

### ESTRUTUA DE COTROLE E DECISÃO
- IF...ELSE
- FOR
- WHILE
- LOOP
- RAISE

#### PROCEDURES AND FUNCTIONS

> Procedures: Bloco responsável por executar código e não retornar valor;
> Functions: Bloco responsável por executar código e retornar valor;
> Para chamar procedure: execute <nomedaprocedure(parametro)>
> Parâmetros: IN (ENTRADA), OUT(SAIDA) E IN OUT (AMBOS);
> IN: Não pode ser modificado, somente input
> OUT: Parâmetro de saída. O seu valor pode ser modificado internamente no código e retornado
> IN OUT: Combinação dos dois.

````

var := 10;
result := -1;
calcula_indice(var, result);
if result = 1 then
    raise erro
end if;


===
CREATE OR REPLACE calcula_indice (P1 IN numberm, sts OUT number)
BEGIN
    IF P1 = 10 THEN
        STS := 0;
    ELSE
        STS := 1;
    END IF;
END
====

```