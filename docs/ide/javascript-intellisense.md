---
title: JavaScript IntelliSense | Microsoft Docs
ms.custom: 
ms.date: 06/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense [JavaScript]
- <reference> JavaScript XML tag
- JavaScript Code Editor
- XML code comments, JavaScript IntelliSense
- reference JavaScript XML tag
- JavaScript, IntelliSense
- code comments, JavaScript IntelliSense
- JavaScript, reference groups
- JavaScript Editor
- reference directives [JavaScript]
- JavaScript, XML documentation comments
- reference groups [JavaScript]
- JavaScript, reference directives
- IntelliSense [JavaScript], about
- IntelliSense extensibility [JavaScript]
- XML documentation comments [JavaScript]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c958958ca3b0621a4e348ebcbc4cffaf35d3cce9
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2018
---
# <a name="javascript-intellisense"></a>JavaScript IntelliSense

[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]poskytuje výkonný JavaScript prostředí okamžitě po nasazení pro úpravy. Používá technologii služby TypeScript na základě jazyka, Visual Studio nabízí širší technologii IntelliSense, podporu pro moderní funkce JavaScript, a zvýšení produktivity funkce, například přechod na definici, refaktoring a další.

> [!NOTE]
> Služba jazyka JavaScript v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] používá nový modul pro službu jazyka (nazývané "Salsa"). Podrobnosti jsou uvedené v tomto tématu a také si můžete přečíst to [příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudio/2016/11/28/more-productive-javascript-in-visual-studio-2017-rc). Nové prostředí úpravy také většinou platí pro Visual Studio Code. Najdete v článku [dokumentace VS Code](https://code.visualstudio.com/docs/languages/javascript) Další informace.

Další informace o funkci IntelliSense obecné sady Visual Studio najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md).

## <a name="whats-new-in-the-javascript-language-service-in-includevsdev15miscincludesvsdev15mdmd"></a>Co je nového ve službě jazyka JavaScript v[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Počínaje [!include[vs_dev15](../misc/includes/vs_dev15_md.md)], JavaScript IntelliSense zobrazí mnohem víc informace uvedené v seznamech parametr a člen.
Toto nové informace jsou poskytovány služba jazyka TypeScript, který používá statické analysis pozadí v době pro lepší pochopení vašeho kódu.
TypeScript pomocí několika zdrojů si tyto informace:

- [IntelliSense podle odvození typu](#TypeInference)
- [IntelliSense podle JSDoc](#JsDoc)
- [Na základě souborů deklarace TypeScript IntelliSense](#TsDeclFiles)
- [Automatické získání definice typu](#Auto)

### <a name="TypeInference"></a>IntelliSense podle odvození typu

V jazyce JavaScript ve většině případů nejsou žádné explicitní typ informace k dispozici. Naštěstí je obvykle poměrně snadno zjistit typ zadaný kontext okolního kódu.
Tento proces se nazývá odvození typu.

K proměnné nebo vlastnosti typ je obvykle typ hodnoty použitý k inicializaci ho nebo poslední přiřazení hodnoty.

```js
var nextItem = 10;
nextItem; // here we know nextItem is a number

nextItem = "box";
nextItem; // now we know nextItem is a string
```

Pro funkci návratový typ lze odvodit z příkazech return.

Pro parametry funkce v současné době není žádné odvození, ale existují způsoby, jak tento problém obejít pomocí JSDoc nebo TypeScript `.d.ts` soubory (viz další oddíly).

Kromě toho je speciální odvození pro následující:

- Třídy "ES3 stylu", zadán pomocí konstruktoru funkce a přiřazení k vlastnosti prototypu.
- Vzory modulu CommonJS stylu, zadaný jako vlastnost přiřazení na `exports` objekt nebo přiřazení `module.exports` vlastnost.

```js
function Foo(param1) {
    this.prop = param1;
}
Foo.prototype.getIt = function () { return this.prop; };
// Foo will appear as a class, and instances will have a 'prop' property and a 'getIt' method.

exports.Foo = Foo;
// This file will appear as an external module with a 'Foo' export.
// Note that assigning a value to "module.exports" is also supported.
```

### <a name="JsDoc"></a>IntelliSense podle JSDoc

Kde odvození typu neposkytuje informace o požadovaného typu (nebo na podporu dokumentace), informace o typu mohou být k dispozici explicitně prostřednictvím poznámky JSDoc.  Umožnit objekt částečně deklarované konkrétního typu, například můžete použít `@type` značky, jak je uvedeno níže:

```js
/**
 * @type {{a: boolean, b: boolean, c: number}}
 */
var x = {a: true};
x.b = false;
x. // <- "x" is shown as having properties a, b, and c of the types specified
```

Jak je uvedeno, se nikdy odvodit parametry funkce. Ale při použití JSDoc `@param` typy značky můžete přidat také parametry funkce.

```js
/**
 * @param {string} param1 - The first argument to this function
 */
function Foo(param1) {
    this.prop = param1; // "param1" (and thus "this.prop") are now of type "string".
}
```

V tématu [tento doc](https://github.com/Microsoft/TypeScript/wiki/JsDoc-support-in-JavaScript) pro poznámky JsDoc aktuálně podporované.

### <a name="TsDeclFiles"></a>Na základě souborů deklarace TypeScript IntelliSense

JavaScript a TypeScript jsou nyní založená na stejnou službu jazyk, budou se moci pracovat způsobem, bohatší. Například JavaScript IntelliSense lze zadat pro hodnoty deklarované v `.d.ts` souboru ([více informací o](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)), a typy, jako je například rozhraní a třídy, které jsou deklarované v TypeScript jsou k dispozici pro použití jako typy v komentářů JsDoc. 

Níže ukážeme jednoduchý příklad TypeScript definiční soubor, který poskytuje tyto informace o typu (přes rozhraní) do souboru jazyka JavaScript v rámci jednoho projektu (s použitím značku JsDoc).

<img src="https://raw.githubusercontent.com/wiki/Microsoft/TypeScript/images/decl1.png" height="400" width="640"/>

### <a name="Auto"></a>Automatické získání definice typu

Na světě TypeScript nejoblíbenější knihovny JavaScript mají příslušných rozhraní API popsaného `.d.ts` soubory a nejběžnější úložiště pro tyto definice je na [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped).

Ve výchozím nastavení, služba jazyka Salsa pokusí zjistit, které knihovny JavaScript jsou používána a automaticky stáhnout a odkazu odpovídající `.d.ts` soubor, který popisuje knihovny, aby bylo možné poskytovat bohatší technologii IntelliSense. Stažení souborů do mezipaměti umístěný ve složce uživatele v `%LOCALAPPDATA%\Microsoft\TypeScript`.

> [!NOTE]
> Tato funkce je **zakázáno** ve výchozím nastavení, pokud se používá `tsconfig.json` konfigurace souboru, ale může být nastaven na povoleno jako další popsané níže.

Aktuálně automatické zjišťování funguje pro závislosti stažený z npm (načtením `package.json` soubor), Bower (načtením `bower.json` soubor) a pro přijít soubory v projektu, které odpovídají seznam zhruba horní části 400 nejoblíbenější knihoven jazyka JavaScript. Pokud máte například `jquery-1.10.min.js` ve vašem projektu soubor `jquery.d.ts` bude načtených a načíst, aby bylo možné zajistit lepší úpravy prostředí. To `.d.ts` soubor bude mít vliv na projekt.

Pokud nechcete použít automatické akvizice, zakažte ho přidáním konfiguračního souboru, jak je uvedeno níže. Můžete stále umístit definiční soubory pro použití přímo v rámci projektu ručně.

## <a name="see-also"></a>Viz také

[Používání atributu IntelliSense](../ide/using-intellisense.md)