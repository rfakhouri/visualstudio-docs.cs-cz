---
title: JavaScript IntelliSense
ms.date: 06/28/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e0efd8393d6324321a505247a3dad171a81a57
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103473"
---
# <a name="javascript-intellisense"></a>JavaScript IntelliSense

[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] poskytuje výkonný JavaScript prostředí okamžitě po nasazení pro úpravy. Používá technologii služby TypeScript na základě jazyka, Visual Studio nabízí širší technologii IntelliSense, podporu pro moderní funkce JavaScript, a zvýšení produktivity funkce, například přechod na definici, refaktoring a další.

> [!NOTE]
> Služba jazyka JavaScript v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] používá nový modul pro službu jazyka (nazývané "Salsa"). Podrobnosti jsou uvedené v tomto tématu a také si můžete přečíst to [příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudio/2016/11/28/more-productive-javascript-in-visual-studio-2017-rc). Nové prostředí úpravy také většinou platí pro Visual Studio Code. Najdete v článku [dokumentace VS Code](https://code.visualstudio.com/docs/languages/javascript) Další informace.

Další informace o funkci IntelliSense obecné sady Visual Studio najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md).

## <a name="whats-new-in-the-javascript-language-service-in-includevsdev15miscincludesvsdev15mdmd"></a>Co je nového ve službě jazyka JavaScript v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Počínaje [!include[vs_dev15](../misc/includes/vs_dev15_md.md)], JavaScript IntelliSense zobrazí mnohem víc informace uvedené v seznamech parametr a člen.
Toto nové informace jsou poskytovány služba jazyka TypeScript, který používá statické analysis pozadí v době pro lepší pochopení vašeho kódu.
TypeScript pomocí několika zdrojů si tyto informace:

- [IntelliSense podle odvození typu](#TypeInference)
- [IntelliSense podle JSDoc](#JsDoc)
- [Na základě souborů deklarace TypeScript IntelliSense](#TsDeclFiles)
- [Automatické získání definice typu](#Auto)

<a name="TypeInference"></a>
### <a name="intellisense-based-on-type-inference"></a>IntelliSense podle odvození typu

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

Pro parametry funkce v současné době není žádné odvození, ale existují způsoby, jak tento problém obejít pomocí JSDoc nebo TypeScript *. d.ts* soubory (viz další oddíly).

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

<a name="JsDoc"></a>
### <a name="intellisense-based-on-jsdoc"></a>IntelliSense podle JSDoc

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

V tématu [JSDoc podpory v jazyce JavaScript](https://github.com/Microsoft/TypeScript/wiki/JsDoc-support-in-JavaScript) pro poznámky JsDoc aktuálně podporované.

<a name="TsDeclFiles"></a>
### <a name="intellisense-based-on-typescript-declaration-files"></a>Na základě souborů deklarace TypeScript IntelliSense

JavaScript a TypeScript jsou nyní založená na stejnou službu jazyk, budou se moci pracovat způsobem, bohatší. Například JavaScript IntelliSense lze zadat pro hodnoty deklarované v *. d.ts* souboru (v tématu [TypeScript dokumentace](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)), a typy, jako je například rozhraní a třídy, které jsou deklarované v TypeScript k dispozici pro použití jako typy v komentářů JsDoc.

Níže ukážeme jednoduchý příklad TypeScript definiční soubor, který poskytuje tyto informace o typu (přes rozhraní) do souboru jazyka JavaScript v rámci jednoho projektu (pomocí `JsDoc` značka).

<img src="https://raw.githubusercontent.com/wiki/Microsoft/TypeScript/images/decl1.png" height="400" width="640" alt="TypeScript definition file" />

<a name="Auto"></a>
### <a name="automatic-acquisition-of-type-definitions"></a>Automatické získání definice typu

Na světě TypeScript nejoblíbenější knihovny JavaScript mají příslušných rozhraní API popsaného *. d.ts* soubory a nejběžnější úložiště pro tyto definice je na [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped).

Ve výchozím nastavení, služba jazyka Salsa pokusí zjistit, které knihovny JavaScript jsou používána a automaticky stáhnout a odkazu k odpovídající položce *. d.ts* soubor, který popisuje knihovny, chcete-li poskytovat bohatší IntelliSense. Stažení souborů do mezipaměti umístěný ve složce uživatele na *%LOCALAPPDATA%\Microsoft\TypeScript*.

> [!NOTE]
> Tato funkce je **zakázáno** ve výchozím nastavení, pokud se používá *tsconfig.json* konfigurace souboru, ale může být nastaven na povoleno jako další popsané níže.

Aktuálně automatické zjišťování funguje pro závislosti stažený z npm (načtením *package.json* soubor), Bower (načtením *bower.json* soubor) a pro přijít soubory v projektu, které odpovídají seznamu knihoven zhruba horní 400 nejoblíbenější jazyk JavaScript. Pokud máte například *jquery 1.10.min.js* ve vašem projektu soubor *jquery.d.ts* bude načtených a načíst, aby bylo možné zajistit lepší úpravy prostředí. To *. d.ts* soubor bude mít vliv na projekt.

Pokud nechcete použít automatické akvizice, zakažte ho přidáním konfiguračního souboru, jak je uvedeno níže. Můžete stále umístit definiční soubory pro použití přímo v rámci projektu ručně.

## <a name="see-also"></a>Viz také

- [Používání atributu IntelliSense](../ide/using-intellisense.md)