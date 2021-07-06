# よくないコード

## 環境分岐

環境を増やしたときに対応が漏れる、影響範囲が大きくなる。  
→機能フラグを使う。

```php
# bad
if (ENVIRONMENT == 'some-environment')
switch (ENVIRONMENT)

# good
if (enabled('some-feature'))
```
