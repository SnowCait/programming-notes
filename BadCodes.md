# よくないコード

## 環境分岐

環境を増やしたときに対応が漏れる、影響範囲が大きくなる。  
→機能フラグを使う。

```php
# bad
if (ENVIRONMENT == 'some-environment')
if (in_array(ENVIRONMENT, ['some-environment-1', 'some-environment-2']))
switch (ENVIRONMENT)

# good
if (enabled('some-feature'))
$value = get('some-feature-value')
```
