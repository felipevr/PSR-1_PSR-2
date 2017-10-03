## PSR-2: Guia de Estilo de Codificação (_Coding Style Guide_)
Este guia é uma extensão do PSR-1 - Padrão Básico de Codificação.

A intenção deste guia é reduzir a discrepância quando códigos de diferentes autores são reaproveitados. Isto é feito utilizando uma série de regras compartilhadas e expectativas sobre como formatar código PHP.

Os tipos das regras são compartilhadas pelos vários membros de projeto. Quando diferentes autores colaboram em múltiplos projetos, ter um guia para ser seguido, auxília na implementação destes projetos. Além disso, o objetivo deste guia não são as regras em si, mas, o compartilhamento destas regras.

As palavras chaves “É OBRIGATÓRIO” (_MUST_) , “NÃO É PERMITIDO” (_MUST NOT_), “É REQUERIDO” (_REQUIRED_), “DEVEM” (_SHALL_), “NÃO DEVEM” (_SHALL NOT_), “DEVERIA” (_SHOULD_), “NÃO DEVERIA” (_SHOULD NOT_), “É RECOMENDADO” (_RECOMMENDED_), “PODE” (_MAY_), e "OPCIONAL” (_OPTIONAL_) nesse documento devem ser interpretadas como no RFC 2119.

### 1. Visão Geral
* Código "É OBRIGATÓRIO" seguir o “_coding style guide_” (guia de estilo de codificalçao) PSR [PSR-1].
* Código "É OBRIGATÓRIO" utiliza 4 espaços de indentação, sem _tabs_.
* “NÃO É PERMITIDO” ter um limite rígido de comprimento/tamanho de linha; o limite "É OBRIGATÓRIO" ser de 120 caracteres; linhas "DEVERIA" ser de 80 caracteres ou menos.
* "É OBRIGATÓRIO" ter uma linha em branco depois de uma declaração de _namespace_, e "É OBRIGATÓRIO" ter uma linha em branco depois de um bloco de declaração _use_.
* Abre chave ( { ) ( { } para classes "É OBRIGATÓRIO" ser na próxima linha, e fecha chave ( } ) "É OBRIGATÓRIO" ser na próxima linha depois do _body_ (corpo de código).
* Abre chave ( { ) para métodos "É OBRIGATÓRIO" ser na próxima linha, e fecha chave ( } ) "É OBRIGATÓRIO" ser na próxima linha depois do _body_ (corpo de código).
* _Visibility_ (Visiabilidade) "É OBRIGATÓRIO" ser declaradas com todas as propriedades e métodos; _abstract_ e final "É OBRIGATÓRIO" serem declaradas antes da _visibility_ (visiabilidade); _static_ "É OBRIGATÓRIO" ser declarado depois da _visibility_ (visiabilidade).
* Palvras chaves de estrutura de controle "É OBRIGATÓRIO" ter um espaço depois de cada declaração; “NÃO É PERMITIDO” espaço nas chamadas de métodos e funções.
* Abre chave ( { ) para estruturas de controle "É OBRIGATÓRIO" serem na mesma linha, e fecha chave ( } ) deve ir na próxima linha depois do _body_ (corpo de código).
* Abre parênteses ( ( ) para estruturas de controle “NÃO É PERMITIDO” ter um espaço depois de cada declaração, e fecha parênteses para estruturas de controle “NÃO É PERMITIDO” terem um espaço antes de cada declaração.

#### 1.1. Exemplo

Este exemplo exemplefica algumas das regras citadas acima:

`<?php`
namespace Vendor\Package;

use FooInterface;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class Foo extends Bar implements FooInterface
{
    public function sampleMethod($a, $b = null)
    {
        if ($a === $b) {
            bar();
        } elseif ($a > $b) {
            $foo->bar($arg1);
        } else {
            BazClass::bar($arg2, $arg3);
        }
    }

    final public static function bar()
    {
        // método body
    }
}

### 2. _General_ (Genérico)
#### 2.1. Padrão Básico de Codificação

Código "É OBRIGATÓRIO" obedecer todas as regras determinadas em PSR-1.

#### 2.2. Arquivos

Todos arquivos PHP "É OBRIGATÓRIO" utilizar o Unix LF (_linefeed_) como fim de linha.

Todos arquivos PHP "É OBRIGATÓRIO" terminar com uma única linha em branco.

O fechamento da _tag_ `?>` "É OBRIGATÓRIO" ser omitida em arquivos que contém unicamente PHP.

#### 2.3. Linhas

“NÃO É PERMITIDO” ter um limite rígido de tamanho/comprimento de linha.

O limite básico de tamanho/comprimento de linha "É OBRIGATÓRIO" ser de 120 caracteres; verificadores automático de estilo (_automated style checkers_) "É OBRIGATÓRIO" alertar (_warning_) mas “NÃO É PERMITIDO” dar erro (_error_) quando utilizado este limite básico.

Linhas "NÃO DEVERIA" ser maiores do que 80 caracteres; linhas maiores que 80 caracteres "DEVERIA" ser quebradas/separadas em múltiplas linhas subsequentes menores que 80 caracteres.

“NÃO É PERMITIDO” ter espaço em branco em fim de linhas que não são em branco.

Linhas em branco "PODE" ser adiciondas para melhorar a legibilidade e para indicar blocos de código.

“NÃO É PERMITIDO” ter mais que uma declaração por linha.

#### 2.4. Indentação

Código "É OBRIGATÓRIO" usar 4 espaços de indentação, e "NÃO É PERMITIDO" usar _tabs_ para indentação.

Utilizar somentes espaços, e não misturar espaços com _tabs_, contribui para evitar problemas de _diffs_, _patches_, _history_ (histórico), e anotações. O uso de espaços também facilita a utilização de sub-indentações para alinhar linhas internas do bloco de código.

#### 2.5. Palavras Chaves e _True_ (Verdadeiro)/_False_ (Falso)/_Null_ (Vazio)

Palavras chaves PHP "É OBRIGATÓRIO" ser em caixa baixa (letra minúscula).

_Constants true_, _false_, and _null_ (constantes/verdadeiro/falso/vazio) "É OBRIGATÓRIO" serem em caixa baixa (letra minúscula).

### 3. _Namespace_ e Declarações

"É OBRIGATÓRIO" ter uma linha em branco depois de uma declaração de _namespace_.

"É OBRIGATÓRIO" que todas as declarações que não sejam de _namespace_  sejam declaradas depois da declaração de _namespace_.

"É OBRIGATÓRIO" que utilize somente uma palavra chave para cada declaração.

"É OBRIGATÓRIO" ter apenas uma linha em branca depois de um bloco _use_.

Por exemplo:

`<?php`
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... Código PHP adicional ...

### 4. Classes, Propriedades, e Métodos

O termo "classe" refere-se a todas as classes, interfaces e _traits_.

#### 4.1. Extensões e Implementação

As extensões e palavras chaves de implementação "É OBRIGATÓRIO" serem declaradas na mesma linha e com o mesmo nome de classe.

Abrir chave para classe "É OBRIGATÓRIO" ser na mesma linha; fechar chave para classe "É OBRIGATÓRIO" ser na próxima linha depois do _body_.

`<?php`
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constantes, propriedades, métodos
}
Listas de implemetações "PODE" ser quebrada em múltiplas linhas, sendo que cada linha é indentanda somente uma vez. O primeiro item da lista "É OBRIGATÓRIO" ser na próxima linha, e "É OBRIGATÓRIO" ter uma única interface por linha.
`<?php`
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // constantes, propriedades, métodos
}
#### 4.2. Propriedades

_Visibility_ (visiabilidade) "É OBRIGATÓRIO" ser declarada com todas as propriedades.

A palavra chave _var_ "NÃO É PERMITIDO" ser usada para declarar uma propriedade.

"NÃO É PERMITIDO" que tenha mais de uma propriedade por declaração.

Nomes de propriedades "NÃO DEVERIA" ser um prefixo com um único subtraço (_) para indicar _protected_ (protegido) ou _private_ (privado) _visibility_ (visiabilidade).

Uma declaração de propriedade é feita como no exemplo abaixo:

`<?php`
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
#### 4.3. Métodos

_Visibility_ (Visiabilidade) "É OBRIGATÓRIO" ser declarada em todos os métodos.

Nomes de métodos "NÃO DEVERIA" ser um prefixo com um único subtraço (_) para indicar _protected_ (protegido) ou _private_ (privado) _visibility_ (visiabilidade).

Nomes de métodos "NÃO É PERMITIDO" ser declarados com uma espaço após um nome de método. Abre chave ( { ) "É OBRIGATÓRIO" irem na mesma linha da declaração do método, e fecha chave ( } ) "É OBRIGATÓRIO" ser na linha após o _body_. "NÃO É PERMITIDO" ter um espaço em branco após abrir parênteses, e "NÃO É PERMITIDO" ter um espaço em branco antes de fechar parênteses.

Segue como seria uma declaração de método. Note a posição dos parênteses, vírgulas, espaços e chaves ({ }):

`<?php`
namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // método _body_
    }
}
#### 4.4. Argumentos dos Métodos

Uma lista de argumentos "NÃO É PERMITIDO" ter um espaço antes de cada vírgula (,), e "É OBRIGATÓRIO" ter um espaço após cada vírgula (,).

Argumentos de métodos com valores _default_ (padrões) "É OBRIGATÓRIO" estarem no final da lista de argumentos.

`<?php`
namespace Vendor\Package;

class ClassName
{
    public function foo($arg1, &$arg2, $arg3 = [])
    {
        // método _body_
    }
}
Listas de argumentos "PODE" ser quebradas em múltiplas linhas, em que cada linha é indentada uma única vez. O primeiro item da lista "É OBRIGATÓRIO" estar na próxima linha, e "É OBRIGATÓRIO" ter um único argumento por linha.

Quando a lista de argumentos é quebrada em múltiplas linhas, fecha ( ) ) parênteses e abre chave ( { ) ( { ) "É OBRIGATÓRIO" estarem juntos na mesma linha com um espaço entre eles.

`<?php`
namespace Vendor\Package;

class ClassName
{
    public function aVeryLongMethodName(
        ClassTypeHint $arg1,
        &$arg2,
        array $arg3 = []
    ) {
        // método _body_
    }
}
#### 4.5. _abstract_ (resumo), _final_, e _static_ (estático)

As declarações _abstract_ (resumo) e _final_ "É OBRIGATÓRIO" preceder a declaração de _visibility_ (visiabilidade).

A declaração _static_ (estático) "É OBRIGATÓRIO" ser feita depois da declaração de  _visibility_ (visiabilidade).

`<?php`
namespace Vendor\Package;

abstract class ClassName
{
    protected static $foo;

    abstract protected function zim();

    final public static function bar()
    {
        // método _body_
    }
}
#### 4.6. Métodos e Chamadas de Funções

Quando for criar um método ou uma chamada de função, "NÃO É PERMITIDO" ter um espaço entre o método ou o nome da função e no abre parênteses ((), "NÃO É PERMITIDO" ter um espaço após abre parênteses ((), e "NÃO É PERMITIDO" ter um espaço antes de fechar parênteses ()). Na lista de argumentos "NÃO É PERMITIDO" ter um espaço antes de cada vírgula, e "É OBRIGATÓRIO" ter um espaço após cada vírgula.

`<?php`
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);

Lista de argumentos "PODE" ser quebrada em múltiplas linhas, cada sublinha é indentada uma únicaz vez. O primeiro item da lista "É OBRIGATÓRIO" estar na próxima linha, e "É OBRIGATÓRIO" ter somente um argumento por linha.

`<?php`
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
### 5. Estruturas de Controle

As regras genéricas para estruturas de conrole são as seguintes:

* "É OBRIGATÓRIO" ter um espaço após uma palavra chave de estrutura de controle.
* "NÃO É PERMITIDO" ter um espaço após abre parênteses ( ( ).
* "NÃO É PERMITIDO" ter um espaço antes fecha parênteses ( ) ).
* "É OBRIGATÓRIO" ter uma espaço entre fecha parênteses ( ) ) e abre chave ( { ).
* A estrutura de _body_ "É OBRIGATÓRIO" ser indentada uma única vez.
* Fecha chave ( } ) "É OBRIGATÓRIO" estar na linha após o _body_.

O _body_ de cada estrutura "É OBRIGATÓRIO" estar entre chaves ({ e }). Este padrão de estrutura reduz os erros quando novas linhas são adicionadas ao _body_.

#### 5.1. _if_ , _elseif_ , _else_

Uma estrutura de _if_ é exemplificada a seguir. Note a posição dos parênteses, espaços e chaves ({ e }); e que _else_ e _elseif_ estão na mesma linha.

`<?php`
if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}

A palavra chave _elseif_ "PODERIA" ser usada ao invés de _else if_, assim todas as palavras chaves de controle seriam a mesma palavra.

#### 5.2. _switch_, _case_

Uma estrutura de _switch_ é exemplificada a seguir. Note a posição dos parênteses, espaços e chaves. "É OBRIGATÓRIO" a estrutura ser indentada uma vez para o _switch_ e outra para o _break_ (ou outra palavra chave de finalização) "É OBRIGATÓRIO" ser indentada no mesmo level do _body_. "É OBRIGATÓRIO" ter um comentário do tipo _// no break_ quando uma finalização é intencional em um _non-empty_ (não vazio) _body_.

`<?php`
switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
#### 5.3. _while_ , _do while_

Uma estrutura de _while_ é exemplificada a seguir. Note a posição dos parênteses, espaõs e chaves ({ e }).

`<?php`
while ($expr) {
    // estrutura do _body_
}

Uma estrutura de _do while_ é exemplificada a seguir. Note a posição dos parênteses, espaõs e chaves ({ e }).

<?php
do {
    // estrutura do _body_
} while ($expr);

#### 5.4. _for_

Uma estrutura de _for_ é exemplificada a seguir. Note a posição dos parênteses, espaõs e chaves ({ e }).

`<?php`
for ($i = 0; $i < 10; $i++) {
    // _for body_
}

#### 5.5. _foreach_

Uma estrutura de _foreach_ é exemplificada a seguir. Note a posição dos parênteses, espaõs e chaves ({ e }).

`<?php`
foreach ($iterable as $key => $value) {
    // _foreach body_
}
#### 5.6. _try_, _catch_

Um bloco de  _try catch_ é exemplifica a seguir. Note a posição dos parênteses, espaõs e chaves ({ e }).

`<?php`
try {
    // _try body_
} catch (FirstExceptionType $e) {
    // _catch body_
} catch (OtherExceptionType $e) {
    // _catch body_
}
### 6. _Closures_ (Fechamentos)

_Closures_ "É OBRIGATÓRIO" ser declara com espaço após uma palavra chave de função, e um espaço antes e após o uso de uma palavra chave.

Abre chave ({) "É OBRIGATÓRIO" ser na mesma linha, e o fecha chave (}) "É OBRIGATÓRIO" ir na linha após o _body_.

"NÃO É PERMITIDO" ter um espaço após abre parênteses (() na lista de argumentos ou na lista de variáveis, e "NÃO É PERMITIDO" ter um espaço antes de fechar parênteses ()) na lista de argumentos ou na lista de variáveis.

Na lista de argumentos e na lista de variáveis, "NÃO É PERMITIDO" ter um espaço antes de cada vírgula, e "É OBRIGATÓRIO" ter um espaço após cada vírgula.

Argumentos _Closure_ com valores padrões "É OBRIGATÓRIO" irem no final da lista de argumentos.

Uma declaração de _closure_ é exempleficada a seguir. Note a posicação dos parênteses, vírgulas, espaçõs e chaves.

`<?php`
$closureWithArgs = function ($arg1, $arg2) {
    // _body_
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // _body_
};

Lista de argumentos e lista de variáveis "PODE" ser quebradas em múltiplas linhas, cada sublinha é indentada uma única vez. O primeiro item da lista "É OBRIGATÓRIO" estar na próxima linha, e "É OBRIGATÓRIO" ter somente um argumento ou variável em cada linha.

Quando o fim da lista é quebrada em múltiplas linhas, o fecha parênteses ()) e abre chaves ({) "É OBRIGATÓRIO" estarem juntos na mesma linha com um espaço entre eles.

Segue um exemplo de _closures_ com/sem lista de argumentos e variáveis quebradas em múltiplas linhas.

`<?php`
$longArgs_noVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) {
    // _body_
};

$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // _body_
};

$longArgs_longVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // _body_
};

$longArgs_shortVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use ($var1) {
    // _body_
};

$shortArgs_longVars = function ($arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // _body_
};

Note que a formatação das regras também se aplicam quando o _closure_ é usado diretamente em uma função ou numa chamada de método como um argumento.

`<?php`
$foo->bar(
    $arg1,
    function ($arg2) use ($var1) {
        // _body_
    },
    $arg3
);
### 7. Conclusão

Há vários elementos de estilo e de prática itencionalmente omitidas neste guia. Segue as que estão incluídas (mas, não são as únicas):

* Declaração de variáveis e constantes globais.
* Declaração de funções.
* Operadores e  _assignment_ (atribuição).
* Indentação de linhas.
* Comentários e documentação em blocos de código.
* Prefixos e sufixos de nomes de classes.
* Boas práticas.
* Recomendações futuras deste guia "PODE" ser revisadas, para que aja uma melhoria dos elementos de estilos e da prática.

### 8. Apêndice

Para escrever este guia de estilos, o grupo fez uma pesquisa com os membros de projetos que possuem práticas comuns de codificação.

#### 8.1. Dados da Pesquisa

url,http://www.horde.org/apps/horde/docs/CODING_STANDARDS,http://pear.php.net/manual/en/standards.php,http://solarphp.com/manual/appendix-standards.style,http://framework.zend.com/manual/en/coding-standard.html,http://symfony.com/doc/2.0/contributing/code/standards.html,http://www.ppi.io/docs/coding-standards.html,https://github.com/ezsystems/ezp-next/wiki/codingstandards,http://book.cakephp.org/2.0/en/contributing/cakephp-coding-conventions.html,https://github.com/UnionOfRAD/lithium/wiki/Spec%3A-Coding,http://drupal.org/coding-standards,http://code.google.com/p/sabredav/,http://area51.phpbb.com/docs/31x/coding-guidelines.html,https://docs.google.com/a/zikula.org/document/edit?authkey=CPCU0Us&hgd=1&id=1fcqb93Sn-hR9c0mkN6m_tyWnmEvoswKBtSc0tKkZmJA,http://www.chisimba.com,n/a,https://github.com/Respect/project-info/blob/master/coding-standards-sample.php,n/a,Object Calisthenics for PHP,http://doc.nette.org/en/coding-standard,http://flow3.typo3.org,https://github.com/propelorm/Propel2/wiki/Coding-Standards,http://developer.joomla.org/coding-standards.html
voting,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,no,no,no,?,yes,no,yes
indent_type,4,4,4,4,4,tab,4,tab,tab,2,4,tab,4,4,4,4,4,4,tab,tab,4,tab
line_length_limit_soft,75,75,75,75,no,85,120,120,80,80,80,no,100,80,80,?,?,120,80,120,no,150
line_length_limit_hard,85,85,85,85,no,no,no,no,100,?,no,no,no,100,100,?,120,120,no,no,no,no
class_names,studly,studly,studly,studly,studly,studly,studly,studly,studly,studly,studly,lower_under,studly,lower,studly,studly,studly,studly,?,studly,studly,studly
class_brace_line,next,next,next,next,next,same,next,same,same,same,same,next,next,next,next,next,next,next,next,same,next,next
constant_names,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper,upper
true_false_null,lower,lower,lower,lower,lower,lower,lower,lower,lower,upper,lower,lower,lower,upper,lower,lower,lower,lower,lower,upper,lower,lower
method_names,camel,camel,camel,camel,camel,camel,camel,camel,camel,camel,camel,lower_under,camel,camel,camel,camel,camel,camel,camel,camel,camel,camel
method_brace_line,next,next,next,next,next,same,next,same,same,same,same,next,next,same,next,next,next,next,next,same,next,next
control_brace_line,same,same,same,same,same,same,next,same,same,same,same,next,same,same,next,same,same,same,same,same,same,next
control_space_after,yes,yes,yes,yes,yes,no,yes,yes,yes,yes,no,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes,yes
always_use_control_braces,yes,yes,yes,yes,yes,yes,no,yes,yes,yes,no,yes,yes,yes,yes,no,yes,yes,yes,yes,yes,yes
else_elseif_line,same,same,same,same,same,same,next,same,same,next,same,next,same,next,next,same,same,same,same,same,same,next
case_break_indent_from_switch,0/1,0/1,0/1,1/2,1/2,1/2,1/2,1/1,1/1,1/2,1/2,1/1,1/2,1/2,1/2,1/2,1/2,1/2,0/1,1/1,1/2,1/2
function_space_after,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no,no
closing_php_tag_required,no,no,no,no,no,no,no,no,yes,no,no,no,no,yes,no,no,no,no,no,yes,no,no
line_endings,LF,LF,LF,LF,LF,LF,LF,LF,?,LF,?,LF,LF,LF,LF,?,,LF,?,LF,LF,LF
static_or_visibility_first,static,?,static,either,either,either,visibility,visibility,visibility,either,static,either,?,visibility,?,?,either,either,visibility,visibility,static,?
control_space_parens,no,no,no,no,no,no,yes,no,no,no,no,no,no,yes,?,no,no,no,no,no,no,no
blank_line_after_php,no,no,no,no,yes,no,no,no,no,yes,yes,no,no,yes,?,yes,yes,no,yes,no,yes,no
class_method_control_brace,next/next/same,next/next/same,next/next/same,next/next/same,next/next/same,same/same/same,next/next/next,same/same/same,same/same/same,same/same/same,same/same/same,next/next/next,next/next/same,next/same/same,next/next/next,next/next/same,next/next/same,next/next/same,next/next/same,same/same/same,next/next/same,next/next/next

#### 8.2. Legenda da Pesquisa

_indent_type_: tipo de indentação. _tab_ = “Utilizar tab”, 2 ou 4 = “número de espaços”

_line_length_limit_soft_: O comprimento limite "_soft_" da linha, em caracteres. ? = não há limite.

_line_length_limit_hard_: O comprimento limite "_hard_" da linha, em caracteres. ? = não há limite.

_class_names_: Como são chamadas os nomes das classes? _lower_ = _lowercase_ , _lower_under_ = _lowercase_ (com subtraços como separadores), _studly_ = _StudlyCase_.

_class_brace_line_: O abre chave ({) para uma classe está na mesma linha da palavra chave _class_, ou está na próxima linha?

_constant_names_: Como são os nomes das constantes? _upper_ = _Uppercase_ (com subtraços como separadores).

_true_false_null_: As palavras chaves _true_, _false_, e _null_ são todas escritas como em _lower case_, ou em _upper case_?

_method_names_: Como são os nomes dos métodos? _camel_ = _camelCase_, _lower_under_ = _lowercase_ (com subtraços como separadores).

_method_brace_line_: O abre chave ({) para um método está na mesma linha do nome do método, ou está na próxima linha?

_control_brace_line_: O abre chave ({) para estrutura de controle está na mesma linha, ou está na próxima linha?

_control_space_after_: Há um espaço após uma palavra chave de estrutura de controle?

_always_use_control_braces_: As estruturas de controle sempre utilizam chaves?

_else_elseif_line_: Quando utilizado _else_ ou _elseif_, eles foram utilizados na mesma linha, ou foram utilizados na próxima linha?

_case_break_indent_from_switch_: Quantas vezes o _case_ e o _break_ foram indentandos para abrir um bloco de _switch_?

_function_space_after_: As chamadas de funções possuem espaço após um nome de função e antes de abre parênteses (()?

_closing_php_tag_required_: Nos arquivos que somente contém PHP, o fechamento da tag `?>` é requerido?

_line_endings_: Que tipo de fim de linha é utilizada?

_static_or_visibility_first_: Qunado é feita a declaração de método, o  _static_ (estático) vem primeiro, ou a _visibility_ vem primeiro?

_control_space_parens_: Na expressão da estrutura de controle, há um espaço após abre parênteses (() e um espaço antes de fecha parênteses ())? Sim = if ( $expr ), Não = if ($expr).

_blank_line_after_php_: Há uma linha em branca após abrir uma tag PHP?

_class_method_control_brace_: Sumário de como abre chave ({) deve ir em classes, métodos e estruturas de controles.

#### 8.3. Resultados da Pesquisa

_indent_type_:
    tab: 7
    2: 1
    4: 14
    
_line_length_limit_soft_:
    ?: 2
    no: 3
    75: 4
    80: 6
    85: 1
    100: 1
    120: 4
    150: 1
    
_line_length_limit_hard_:
    ?: 2
    no: 11
    85: 4
    100: 3
    120: 2
    
_class_names_:
    ?: 1
    lower: 1
    lower_under: 1
    studly: 19
    
_class_brace_line_:
    next: 16
    same: 6
    
_constant_names_:
    upper: 22
    
_true_false_null_:
    lower: 19
    upper: 3
    
_method_names_:
    camel: 21
    lower_under: 1
    
_method_brace_line_:
    next: 15
    same: 7
    
_control_brace_line_:
    next: 4
    same: 18
    
_control_space_after_:
    no: 2
    yes: 20
    
_always_use_control_braces_:
    no: 3
    yes: 19
    
_else_elseif_line_:
    next: 6
    same: 16
    
_case_break_indent_from_switch_:
    0/1: 4
    1/1: 4
    1/2: 14
    
_function_space_after_:
    no: 22
    
_closing_php_tag_required_:
    no: 19
    yes: 3
_line_endings_:
    ?: 5
    LF: 17
    
_static_or_visibility_first_:
    ?: 5
    either: 7
    static: 4
    visibility: 6
    
_control_space_parens_:
    ?: 1
    no: 19
    yes: 2
    
_blank_line_after_php_:
    ?: 1
    no: 13
    yes: 8
    
_class_method_control_brace_:
    next/next/next: 4
    next/next/same: 11
    next/same/same: 1
    same/same/same: 6obi
