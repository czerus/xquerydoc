# library module: XQDocComments




## Table of Contents

* Variables: [$MAP0](#var_MAP0), [$MAP1](#var_MAP1), [$MAP2](#var_MAP2), [$INITIAL](#var_INITIAL), [$TRANSITION](#var_TRANSITION), [$EXPECTED](#var_EXPECTED), [$TOKEN](#var_TOKEN), [$lk](#var_lk), [$b0](#var_b0), [$e0](#var_e0), [$l1](#var_l1), [$b1](#var_b1), [$e1](#var_e1), [$error](#var_error), [$result](#var_result)
* Functions: [match\#3](#func_match_3), [transition\#7](#func_transition_7), [token\#3](#func_token_3), [expected-token-set\#1](#func_expected-token-set_1), [map2\#3](#func_map2_3), [error-message\#2](#func_error-message_2), [shift\#3](#func_shift_3), [lookahead1\#3](#func_lookahead1_3), [reduce\#3](#func_reduce_3), [parse-TaggedContents\#2](#func_parse-TaggedContents_2), [parse-DirAttributeValue-1\#2](#func_parse-DirAttributeValue-1_2), [parse-DirAttributeValue-2\#2](#func_parse-DirAttributeValue-2_2), [parse-DirAttributeValue\#2](#func_parse-DirAttributeValue_2), [parse-DirAttrConstructor\#2](#func_parse-DirAttrConstructor_2), [parse-DirElemConstructor-1\#2](#func_parse-DirElemConstructor-1_2), [parse-DirElemConstructor-2\#2](#func_parse-DirElemConstructor-2_2), [parse-DirElemConstructor\#2](#func_parse-DirElemConstructor_2), [parse-Contents-1\#2](#func_parse-Contents-1_2), [parse-Contents\#2](#func_parse-Contents_2), [parse-XQDocComment-1\#2](#func_parse-XQDocComment-1_2), [parse-XQDocComment\#2](#func_parse-XQDocComment_2), [parse-Comment-1\#2](#func_parse-Comment-1_2), [parse-Comment\#2](#func_parse-Comment_2), [parse-Comments-1\#2](#func_parse-Comments-1_2), [parse-Comments\#2](#func_parse-Comments_2), [parse-Comments\#1](#func_parse-Comments_1)


## Variables

### <a name="var_MAP0"/> $MAP0
```xquery
$MAP0 as  xs:integer+
```



### <a name="var_MAP1"/> $MAP1
```xquery
$MAP1 as  xs:integer+
```



### <a name="var_MAP2"/> $MAP2
```xquery
$MAP2 as  xs:integer+
```



### <a name="var_INITIAL"/> $INITIAL
```xquery
$INITIAL as  xs:integer+
```



### <a name="var_TRANSITION"/> $TRANSITION
```xquery
$TRANSITION as  xs:integer+
```



### <a name="var_EXPECTED"/> $EXPECTED
```xquery
$EXPECTED as  xs:integer+
```



### <a name="var_TOKEN"/> $TOKEN
```xquery
$TOKEN as  xs:string+
```



### <a name="var_lk"/> $lk
```xquery
$lk as 
```



### <a name="var_b0"/> $b0
```xquery
$b0 as 
```



### <a name="var_e0"/> $e0
```xquery
$e0 as 
```



### <a name="var_l1"/> $l1
```xquery
$l1 as 
```



### <a name="var_b1"/> $b1
```xquery
$b1 as 
```



### <a name="var_e1"/> $e1
```xquery
$e1 as 
```



### <a name="var_error"/> $error
```xquery
$error as 
```



### <a name="var_result"/> $result
```xquery
$result as 
```





## Functions

### <a name="func_match_3"/> match\#3
```xquery
match($input as xs:string,
                         $begin as xs:integer,
                         $token-set as xs:integer
) as  xs:integer+
```



#### Params

* input as  xs:string the input string.

* begin as  xs:integer the index where to start in input string.

* token-set as  xs:integer the expected token set id.


#### Returns
*  xs:integer+: a sequence of three: the token code of the result token, with input string begin and end positions. If there is no valid token, return the negative id of the DFA state that failed, along with begin and end positions of the longest viable prefix.

### <a name="func_transition_7"/> transition\#7
```xquery
transition($input as xs:string,
                              $begin as xs:integer,
                              $current as xs:integer,
                              $end as xs:integer,
                              $result as xs:integer,
                              $current-state as xs:integer,
                              $previous-state as xs:integer
) as  xs:integer+
```



#### Params

* input as  xs:string the input string.

* begin as  xs:integer the begin index of the current token in the input string.

* current as  xs:integer the index of the current position in the input string.-state the current DFA state.

* end as  xs:integer the end index of the result in the input string.

* result as  xs:integer the result code.

* current-state as  xs:integer the current DFA state.

* previous-state as  xs:integer the previous DFA state.


#### Returns
*  xs:integer+: a sequence of three: the token code of the result token, with input string begin and end positions. If there is no valid token, return the negative id of the DFA state that failed, along with begin and end positions of the longest viable prefix.

### <a name="func_token_3"/> token\#3
```xquery
token($result as xs:string*,
                         $chunk as xs:integer,
                         $base-token-code as xs:integer
) as  xs:string*
```



#### Params

* result as  xs:string\* the result of previous recursion levels.

* chunk as  xs:integer the 32-bit chunk of the expected token bitset.

* base-token-code as  xs:integer the token code of bit 0 in the current chunk.


#### Returns
*  xs:string\*: the set of token strings.

### <a name="func_expected-token-set_1"/> expected-token-set\#1
```xquery
expected-token-set($state as xs:integer
) as  xs:string*
```



#### Params

* state as  xs:integer the DFA state.


#### Returns
*  xs:string\*: the set of token strings

### <a name="func_map2_3"/> map2\#3
```xquery
map2($c as xs:integer, $lo as xs:integer, $hi as xs:integer
) as  xs:integer
```



#### Params

* c as  xs:integer the codepoint.

* lo as  xs:integer the binary search lower bound map index.

* hi as  xs:integer the binary search upper bound map index.


#### Returns
*  xs:integer: the character class.

### <a name="func_error-message_2"/> error-message\#2
```xquery
error-message($input as xs:string, $error as element(error)
) as  xs:string
```



#### Params

* input as  xs:string the input string.

* error as  element(error) the parsing error descriptor.


#### Returns
*  xs:string: the error message.

### <a name="func_shift_3"/> shift\#3
```xquery
shift($code as xs:integer, $input as xs:string, $state as item()+
) as  item()+
```



#### Params

* code as  xs:integer the expected token.

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_lookahead1_3"/> lookahead1\#3
```xquery
lookahead1($set as xs:integer, $input as xs:string, $state as item()+
) as  item()+
```



#### Params

* set as  xs:integer the code of the DFA entry state for the set of valid tokens.

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_reduce_3"/> reduce\#3
```xquery
reduce($state as item()+, $name as xs:string, $count as xs:integer
) as  item()+
```



#### Params

* state as  item()+ the parser state.

* name as  xs:string the name of the result node.

* count as  xs:integer the number of child nodes.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-TaggedContents_2"/> parse-TaggedContents\#2
```xquery
parse-TaggedContents($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirAttributeValue-1_2"/> parse-DirAttributeValue-1\#2
```xquery
parse-DirAttributeValue-1($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirAttributeValue-2_2"/> parse-DirAttributeValue-2\#2
```xquery
parse-DirAttributeValue-2($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirAttributeValue_2"/> parse-DirAttributeValue\#2
```xquery
parse-DirAttributeValue($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirAttrConstructor_2"/> parse-DirAttrConstructor\#2
```xquery
parse-DirAttrConstructor($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirElemConstructor-1_2"/> parse-DirElemConstructor-1\#2
```xquery
parse-DirElemConstructor-1($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirElemConstructor-2_2"/> parse-DirElemConstructor-2\#2
```xquery
parse-DirElemConstructor-2($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-DirElemConstructor_2"/> parse-DirElemConstructor\#2
```xquery
parse-DirElemConstructor($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Contents-1_2"/> parse-Contents-1\#2
```xquery
parse-Contents-1($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Contents_2"/> parse-Contents\#2
```xquery
parse-Contents($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-XQDocComment-1_2"/> parse-XQDocComment-1\#2
```xquery
parse-XQDocComment-1($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-XQDocComment_2"/> parse-XQDocComment\#2
```xquery
parse-XQDocComment($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Comment-1_2"/> parse-Comment-1\#2
```xquery
parse-Comment-1($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Comment_2"/> parse-Comment\#2
```xquery
parse-Comment($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Comments-1_2"/> parse-Comments-1\#2
```xquery
parse-Comments-1($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Comments_2"/> parse-Comments\#2
```xquery
parse-Comments($input as xs:string, $state as item()+
) as  item()+
```



#### Params

* input as  xs:string the input string.

* state as  item()+ the parser state.


#### Returns
*  item()+: the updated parser state.

### <a name="func_parse-Comments_1"/> parse-Comments\#1
```xquery
parse-Comments($s as xs:string
) as  item()*
```



#### Params

* s as  xs:string the string to be parsed.


#### Returns
*  item()\*: the result as generated by parser actions.





*Generated by [xquerydoc](https://github.com/xquery/xquerydoc)*