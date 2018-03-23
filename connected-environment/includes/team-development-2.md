2. Stiskněte F5 (nebo typ `vsce up` v okně Terminálové) ke spuštění služby. Tato funkce se automaticky spustí ho v našem prostoru nově vybranou `scott`. 
1. To může potvrdit, spuštěním `vsce list` znovu. První, můžete si všimnout instance `mywebapi` je nyní spuštěna v `scott` místa (verze provozován `mainline` je stále spuštěná, ale není uveden). Za druhé, přístup bodu adresy URL pro `webfrontend` je s předponou text "scott –". Tato adresa URL je jedinečná `scott` místo a označuje, že požadavky odeslané na adresu"scott" se pokusí o první trasy pro služby `scott` místo a vrátí ke službám v `mainline` místa.

```
Name         Space     Chart              Ports   Updated     Access Points
-----------  --------  -----------------  ------  ----------  -------------
mywebapi     scott     mywebapi-0.1.0     80/TCP  15s ago     http://localhost:61466
webfrontend  mainline  webfrontend-0.1.0  80/TCP  5h ago      https://scott-webfrontend-contosodev.vsce.io
```

![](../media/space-routing.png)

Tato integrované funkce umožňuje připojení prostředí testování kódu začátku do konce ve sdílené evironment bez nutnosti každý vývojář se znovu vytvořit úplné zásobníku služeb v jejich místo. Všimněte si, že tento směrování vyžaduje šíření hlavičky k přeposlání v kódu aplikace, jak je ukázáno v předchozím kroku tohoto průvodce.

## <a name="test-code-in-a-space"></a>Testování kódu v prostoru
K otestování naší nové verze `mywebapi` ve spojení s `webfrontend`, otevřete prohlížeč na adresu URL bodu veřejný přístup pro webfrontend a přejít na stránku o. Měli byste vidět novou zprávu zobrazí.

Nyní odebrat část "scott-" adresy URL a aktualizujte stránku prohlížeče. Měli byste vidět staré chování (vykazují `mywebapi` verze spuštěné v `mainline`).