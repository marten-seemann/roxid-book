# Anpassen der Icons

ROXID verwendet an vielen Stellen die Webfont-Icons von [FontAwesome](http://fontawesome.io).

Sie können das verwendete Icon leicht auswechseln, ohne irgendwelche Anpassungen an TPL-Dateien vorzunehmen. Alle Icons werden im `$icons`-Array in der `application/views/roxidx/icon_config.php` definiert. Sie können durch Neudefinition des Array-Keys in der `application/views/roxid_mod/icon_config.php` überschrieben werden.


## Beispiel

Nehmen wir an, Sie möchten das Icon [cart-arrow-down](https://fortawesome.github.io/Font-Awesome/icon/cart-arrow-down/) für die *In den Warenkorb*-Buttons verwenden.
Fügen Sie dazu den entsprechenden Eintrag in das `$icons`-Array in der `application/views/roxid_mod/icon_config.php` hinzu:

```php
$icons = array(
  'to_basket' => 'fa-cart-arrow-down',
);
```
