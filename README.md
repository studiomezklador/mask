# mask
Mask is a PHP trait that functions as a basic PHP template engine

## Tutorial

__create a simple view to hold ALL view logic__
```php

class MyView
{
    protected $title = 'Hello';
    protected function logic()
    {
        return 'World!';
    }
}
```

__add mask__
```php

use Taviroquai\Mask\Mask;

class MyView
{
    use Mask;
    
    protected $title = 'Hello';
    protected function logic()
    {
        return 'World!';
    }
}
```

__now create an HTML file: template.html__
```html
<p>
{{ title }}
{{ if logic }}{{ logic }}{{ endif }}
</p>
```

__finally use it in PHP as__
```php

$view = new MyView;
echo $view->mask('template');

```

__output:__
```html
<p>
Hello
World!
</p>
```

## API
### Call variables and methods
{{ variableName }}
{{ methodName }}

### Conditions
{{ if methodOrVariableName }}
... something ...
{{ endif }}

### Foreach loops
{{ for variable as local }}  
    {{ local }}  
{{ endfor }}  

### Includes
__include partial.html__  
{{ include partial }}
