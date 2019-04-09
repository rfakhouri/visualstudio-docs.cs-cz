---
title: Pseudoproměnné | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Watch window, pseudovariables
- debugging [Visual Studio], pseudovariables
- pseudovariables
ms.assetid: fae84f68-2138-4144-9bd4-c9e271b6182a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dbfd275625e949e87e2b4109e1d56eaeaf9d7e3c
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59366845"
---
# <a name="pseudovariables-in-the-visual-studio-debugger"></a>Pseudoproměnné v ladicím programu sady Visual Studio
Pseudoproměnné jsou podmínky, které slouží k zobrazení určitých informací v okně proměnné nebo **QuickWatch** dialogové okno. Pseudoproměnnou můžete zadat stejným způsobem, zadali byste jako běžné proměnné. Pseudoproměnné nejsou proměnné, ale a nemusí odpovídat názvům proměnných v programu.

## <a name="example"></a>Příklad
 Předpokládejme, že píšete aplikaci v nativním kódu a chcete zjistit počet popisovačů přidělených v aplikaci. V **Watch** okna, můžete zadat následující pseudoproměnnou **název** sloupce, poté stiskem klávesy ENTER ji vyhodnotit:

`$handles`

 V nativním kódu můžete použít pseudoproměnné uvedené v následující tabulce:

|Pseudoproměnnou|Funkce|
|--------------------|--------------|
|`$err`|Zobrazí poslední chybovou hodnotu nastavenou pomocí funkce SetLastError. Zobrazená hodnota představuje, co by vrátila Funkce GetLastError.<br /><br /> Použití `$err,hr` Chcete-li zobrazit dekódovanou formu této hodnoty. Například, pokud byla poslední chyba 3 `$err,hr` zobrazí `ERROR_PATH_NOT_FOUND : The system cannot find the path specified.`|
|`$handles`|Zobrazí počet popisovačů přidělených v aplikaci.|
|`$vframe`|Zobrazí adresu aktuální rámec zásobníku.|
|`$tid`|Zobrazí identifikátor ID vlákna pro aktuální vlákno.|
|`$env`|Zobrazí zadaný blok prostředí v prohlížeči řetězce.|
|`$cmdline`|Zobrazí řetězec příkazového řádku, který spustil program.|
|`$pid`|Zobrazuje id procesu.|
|`$` *registername –*<br /><br /> or<br /><br /> `@` *registername –*|Zobrazí obsah registru *registername –*.<br /><br /> Obsah registru za normálních okolností lze zobrazit pouze zadáním názvu registru. Je třeba použít tuto syntaxi se pouze když název registru přetíží název proměnné. Pokud název registru je stejný jako název proměnné v aktuálním oboru, ladicí program interpretuje název jako název proměnné. Právě to `$` *registername –* nebo `@` *registername –* se hodí.|
|`$clk`|Zobrazí čas v hodinových cyklech.|
|`$user`|Zobrazí se struktura s informacemi o účtu pro účet, který spouští aplikaci. Z bezpečnostních důvodů nejsou informace heslu zobrazeny.|
|`$exceptionstack`|Zobrazí trasování zásobníku aktuální výjimky prostředí Windows Runtime. `$ exceptionstack` funguje pouze v aplikacích pro UPW. `$ exceptionstack` není podporováno pro výjimky C++ a SEH|
|`$returnvalue`|Zobrazuje hodnotu vrácenou metody rozhraní .NET Framework.|

 V C# můžete použít pseudoproměnné uvedené v následující tabulce:

|Pseudoproměnnou|Funkce|
|--------------------|--------------|
|`$exception`|Zobrazí informace o poslední výjimce. Pokud k žádné výjimce, hodnocení `$exception` zobrazí chybovou zprávu.<br /><br /> Pokud je zakázán Pomocník pro výjimky, `$exception` se automaticky přidá do **lokální** okno, když dojde k výjimce.|
|`$user`|Zobrazí se struktura s informacemi o účtu pro účet, který spouští aplikaci. Z bezpečnostních důvodů nejsou informace heslu zobrazeny.|
|`$returnvalue`|Zobrazuje hodnotu vrácenou metody rozhraní .NET Framework.|

 V jazyce Visual Basic můžete použít pseudoproměnné uvedené v následující tabulce:

|Pseudoproměnnou|Funkce|
|--------------------|--------------|
|`$exception`|Zobrazí informace o poslední výjimce. Pokud k žádné výjimce, hodnocení `$exception` zobrazí chybovou zprávu.|
|`$delete` or `$$delete`|Odstraní implicitní proměnné, který byl vytvořen v **okamžité** okna. Syntaxe je `$delete,` *proměnnou* nebo`$delete,` *proměnné*`.`|
|`$objectids` or `$listobjectids`|Zobrazí všechny aktivní ID objektů jako podřízené položky, z určeného výrazu. Syntaxe je `$objectid,` *výraz* nebo`$listobjectids,` *výraz*`.`|
|`$` *N* `#`|Zobrazí objekt s ID objektu rovna *N*.|
|`$dynamic`|Zobrazí zvláštní **dynamického zobrazení** uzlu pro objekt, který implementuje `IDynamicMetaObjectProvider`. rozhraní. Syntaxe je `$dynamic,` *objekt*. Tato funkce se vztahuje pouze na kód, který používá rozhraní .NET Framework verze 4.|

## <a name="see-also"></a>Viz také
- [Kukátko a Rychlé kukátko Windows](../debugger/watch-and-quickwatch-windows.md)
- [Okna proměnných](../debugger/debugger-windows.md)
