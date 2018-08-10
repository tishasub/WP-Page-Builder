# Dimension
A Dimension Number Input Field

## Parameters
Parameter | Type | Value
--- | --- | ---
type | `required` | Predefined String (textarea)
title | `optional` | String
desc | `optional` | String
responsive | `optional` | Boolean ( Default:false )
std | `optional` | Array

## Return
Always return `object`

## Example
**Responsive**
```php
'addon_dimension' => array(
	'type' => 'dimension',
	'title'	=> __('Dimension Field','your-textdomain'),
	'std' => array(
		'md' => array( 'top' => '10px', 'right' => '0px', 'bottom' => '0px', 'left' => '0px' ),
		'sm' => array( 'top' => '9px', 'right' => '0px', 'bottom' => '0px', 'left' => '0px' ),
		'xs' => array( 'top' => '7px', 'right' => '0px', 'bottom' => '0px', 'left' => '0px' ),
		),
	'unit' => array( 'px','em','%' ),
	'responsive' => true,
	'selector' => '{{SELECTOR}} .example-dimension{ margin: {{data.addon_dimension}}; }'
)
```

**Not Responsive**
```php
'addon_dimension' => array(
	'type' => 'dimension',
	'title'	=> __('Dimension Field','your-textdomain'),
	'std' => array(
                'top' => '10px', 
                'right' => '0px', 
                'bottom' => '0px', 
                'left' => '0px'
            ),
	'unit' => array( 'px','em','%' ),
	'selector' => '{{SELECTOR}} .example-dimension{ margin: {{data.addon_dimension}}; }'
)
```

**Not Responsive Without Unit**
```php
'addon_dimension' => array(
	'type' => 'dimension',
	'title'	=> __('Dimension Field','your-textdomain'),
	'std' => array( 
                'top' => '10',
                'right' => '0',
                'bottom' => '0',
                'left' => '0'
            ),
)
```


## Controls
### PHP
Inside the `rander()` method

**Responsive**
```php
foreach( $value["top"] as $key => $value ){
    echo '<div>'.$value["top"].'</div>';
    echo '<div>'.$value["right"].'</div>';
    echo '<div>'.$value["bottom"].'</div>';
    echo '<div>'.$value["left"].'</div>';
}
```

**Not Responsive**
```php
echo '<div>'.$data["settings"]["addon_dimension"]["top"].'</div>';
echo '<div>'.$data["settings"]["addon_dimension"]["right"].'</div>';
echo '<div>'.$data["settings"]["addon_dimension"]["bottom"].'</div>';
echo '<div>'.$data["settings"]["addon_dimension"]["left"].'</div>';
```

**Not Responsive Without Unit**
```php
echo '<div>'.$data["settings"]["addon_dimension"]["top"].'</div>';
echo '<div>'.$data["settings"]["addon_dimension"]["right"].'</div>';
echo '<div>'.$data["settings"]["addon_dimension"]["bottom"].'</div>';
echo '<div>'.$data["settings"]["addon_dimension"]["left"].'</div>';
```

### JS Template
Inside the `getTemplate()` method-

**Responsive**
```js
<div>
<# _.forEach(data.addon_dimension, function(value, key) { #>
    {{value.top}}
    {{value.right}}
    {{value.bottom}}
    {{value.left}}
<# } #>
</div>
```

**Not Responsive**
```js
<div>{{data.addon_dimension}}</div>
```

**Not Responsive Without Unit**
```js
<div>{{data.addon_dimension}}</div>
```