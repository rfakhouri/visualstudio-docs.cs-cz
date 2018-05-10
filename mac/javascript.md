---
title: JavaScript
description: Informace o podporu pro jazyk Javascript v sadě Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 61432695-5B12-4257-B250-48D37EED106D
ms.openlocfilehash: b24591053162603ed3089c0868d215a101688f7e
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="javascript-support"></a>Podpora jazyka JavaScript

Visual Studio pro Mac poskytuje podporu pro Javascript a Typescript zvýraznění syntaxe, formátování kódu a technologii IntelliSense. 

![Podpora editor typescript](https://msdnshared.blob.core.windows.net/media/2018/03/TypeScript-editor.gif)

Další informace o zápisu JavaScript, najdete v sekci [psaní kódu jazyka Javascript](https://docs.microsoft.com/scripting/javascript/writing-javascript-code) příručky.

## <a name="adding-a-javascript-file"></a>Přidání souboru jazyka JavaScript

Soubory JavaScript se nejčastěji používá přidají do projektů ASP.NET Core prostřednictvím **nový soubor** dialogové okno. Chcete-li přidat soubor javascript, klikněte pravým tlačítkem na projekt a přejděte na **Přidat > Nový soubor**: 

![Přidání nové soubory do projektu](media/javascript-image1.png)

Z tohoto dialogového okna nový soubor vyberte **webové > soubor prázdný JS** nebo **webové > Typescript souboru**. Pojmenujte ho a potom zvolte **nový**:

![Vytvoření nového souboru typescript ze šablony](media/javascript-image2.png)

## <a name="intellisense"></a>IntelliSense

Visual Studio pro Mac používá [služba jazyka Javascript](https://docs.microsoft.com/en-us/visualstudio/ide/javascript-intellisense) na poskytovat technologii Intellisense, což umožňuje mít doplňování kódu pro inteligentní, informace o parametrech a seznamech členů k zápisu kódu.

JavaScript intellisense v sadě Visual Studio pro Mac může být založen na odvození typu, JSDoc nebo Typescript deklarace.

- **Odvození typu** – typ objektu je započítáno podle okolního kontext kódu. Další informace najdete v tématu část sady Visual Studio na [IntelliSense podle odvození typu](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense#intellisense-based-on-type-inference).
- **JSDoc** – nastanou chvíle, kdy odvození typu neposkytuje informace správného typu. V těchto případech lze explicitně pomocí zadat informace o typu [JSDoc](http://usejsdoc.org/about-getting-started.html) poznámky. Další informace najdete v tématu část sady Visual Studio na [Intellisense podle JSDoc](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense#intellisense-based-on-jsdoc)
- **Soubory typeScript deklarace** – `.d.ts` soubory se používají k zadání hodnot pro Javascript Intellisense. Typy deklarovaného v souboru lze použít jako typy na komentářů JSDoc. Další informace najdete v tématu část sady Visual Studio na [IntelliSense na základě TypeScript deklarace souborů](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense#intellisense-based-on-typescript-declaration-files) ![přidání soubor definice typescript](media/javascript-image3.png)