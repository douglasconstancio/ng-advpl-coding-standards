# AdvPL Coding Standards

### Arquivo

- A extensão deve ser minúscula (exemplo: `.prw`, `.apw`)

### Estilo

- Tabs somente para indentação, não para separação (ou seja, usar tabs somente à esquerda, antes de iniciar a linha, nunca no meio da linha)
- Nome de variáveis devem se basear na notação húngara (iniciar por `n-números`, `c-char/string`, `l-boolean`, `a-array/matriz`, `o-objetos` e `x-indefinido`, `b-bloco de código` )
- Evite nomes de variáveis como `nX` ou `nY` (exceto para índices). Seja mais descritivo
- Palavras-chave da linguagem devem usar **UpperCamelCase** (exemplos: `If`, `EndIf`, `While`)
- Ao terminar uma instrução `Do While`, prefira `EndDo` ao invés de somente `End`
- Ao terminar uma instrução `For`, prefira `Next <variable>` ao invés de somente `Next`
- Nomes de variáveis locais devem ser em **lowerCamelCase** (exemplos: `cName`, `nAge`)
- Nomes de funções em notação húngara devem usar **lowerCamelCase** (exemplo: `aAdd`)
- Use as variáveis com nomes iguais em tamanho e caixa (não faça `thisIsMyVari` e `THISISMYVARI`)
- Nomes de funções sem notação húngara devem usar **UpperCamelCase** (exemplo: `RetSqlName`)
- Deve haver 1 espaço entre os argumentos de função, blocos e arrays (exemplo: `RetSqlName( 'STJ' )`)
- Deve haver 1 espaço após cada vírgula (exemplo: `{ 1, 2, 3 }`)

> estoura muito rápido o espaçamento, sendo que já pede 80 colunas no fonte.
Ruim: Function( 'STJ' , .T. )
Bom: Function('STJ', .T.)

> If Function( cVal1, nVariable, cVal1, nVariable, cVal1, nVariable, cVal1, nVariable, cVal1, nVariable)

- Deve haver espaço entre parâmetros de funções (use `Call( 1, 2, 3 )` e não `Call(1,2,3)`)
- Evite ultrapassar 80 colunas horizontalmente. Quebre o código com `;` quando necessário

> sugestao de 140

- Valores lógicos devem usar caixa alta (exemplo: `.F.`)
- Espaço entre operadores. Use `nValue > nExpected` ao invés de `nValue>nExpected`
- `Return` indentado, já que faz parte da estrutura da função e **não** é um terminador

Function Xis()

	Local abc
	If
	EndIf

Return Nil

- Em comentários, 1 espaço após `//`

> If nLocal > 0 //Comentario. Não concordamos que seja uma boa prática.

- Idioma padronizado. Evite misturar português e inglês quando possível
> ok, padrão é não misturar, mas não se define qual a língua padrão

- Deixar 1 linha em branco para cada *statement*, exceto conjuntos de *statements*

Local lRet
Local lOk

Local cMoto

Private nMacas

Private cCaminhao

> nao vemos muito sentido, deixamos tudo junto mas ordenado por tipagem

- Deixar 1 linha vazia no final de cada arquivo
> por que?

- Prefira aspas simples `'` ao invés de duplas `"`
> aspas simples facilita a leitura
dbSelectArea("STJ")
dbSelectArea('STJ')
alert('a "citação" é boa ') -> pelo portugues exige usar aspas duplas dentro
> podemos fazer votação

- Para acesso de índices múltiplos, evite `aList[ nI ][ nJ ]`. Use `aList[ nI, nJ ]`
> com vírgula economizamos caracteres

- Funções **não** devem receber mais que 6 parâmetros
> qual o motivo?

- Evite aninhamentos com mais de 3 statements (exemplo: `If` dentro de `If` dentro de `If`)


- Use `!=` ao invés de `<>`
- Não faça `== .T.`
- Use `!` ao invés de `.Not.`


## Redundância

- Substitua `If` dentro de `If` por `.And.`

## Funcionamento

- Lembre-se de, ao criar uma tabela temporária, fechá-la com `dbCloseArea`
- Lembre-se de fechar o _handler_ para o arquivo com `fClose` ao usar `fOpen`
- Quando deslocar para outro registro utilizando `dbSkip`, garanta estar posicionado na tabela desejada, caso contrário utilize `TABLE->( dbSkip() )` ou então utilize `dbSelectArea( TABLE )` antes do `dbSkip()`


+ nao usar variaveis x ou y, etc.
+ Static fValid

## Referências

https://github.com/haskellcamargo/advpl-coding-standards by @haskellcamargo
