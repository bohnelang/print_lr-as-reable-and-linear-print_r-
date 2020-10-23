# PHP print_lr() 

This few lines of php code outputs a strong nested array /object-tree in a readble way:

```
print_r():
Array
(
    [items] => Array
        (
            [0] => Array
                (
                    [title] => Array
                        (
                            [0] => Array
                                (
                                    [language] => en
                                    [title] => Journal of Mass Spectrometry
                                    [language_phrases] => Array
                                        (
                                            [0] => Array
                                                (
                                                    [value] => en
                                                    [phrase] => English
                                                    [language] => en
                                                )

                                        )

                                )

                        )
```


```
printlr():

[items][0][title][0][title]=Journal of Mass Spectrometry
[items][0][title][0][language_phrases][0][value]=en
[items][0][title][0][language_phrases][0][language]=en
[items][0][title][0][language_phrases][0][phrase]=English
[items][0][title][0][language]=en
```

This is a small recursiv function in php that walk through the nested structure and outputs the values:
```
function print_lr($arr,$display="") {
  foreach ($arr as $key => $value)  (is_array($value)||is_object($value))?print_lr($value, sprintf("%s[%s]",$display,$key)):printf("%s[%s]=%s\n",$display,$key,$value);
}

```
