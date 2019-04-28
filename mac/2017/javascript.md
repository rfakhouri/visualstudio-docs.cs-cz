---
title: JavaScript a TypeScript
description: Informace o podpoře pro jazyk JavaScript v sadě Visual Studio pro Mac
author: conceptdev
ms.author: crdun
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 61432695-5B12-4257-B250-48D37EED106D
ms.openlocfilehash: ed84e5478ae7a15905a5555a318bd656c664710e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62997490"
---
# <a name="javascript-and-typescript-support"></a>Podpora jazyka JavaScript a TypeScript

Visual Studio pro Mac poskytuje podporu pro JavaScript a TypeScript prostřednictvím zvýrazňování syntaxe, formátování kódu a technologii IntelliSense.

![Podpora editoru typescript](https://msdnshared.blob.core.windows.net/media/2018/03/TypeScript-editor.gif)

Další informace o psaní jazyka JavaScript naleznete v části [psaní kódu jazyka JavaScript](/scripting/javascript/writing-javascript-code) vodítka.

## <a name="adding-a-javascript-file"></a>Přidání souboru jazyka JavaScript

Soubory jazyka JavaScript jsou nejčastěji přidat do projektů ASP.NET Core prostřednictvím **nový soubor** dialogového okna. Chcete-li přidat soubor jazyka javascript, klikněte pravým tlačítkem na projekt a přejděte na **Přidat > Nový soubor**:

![přidávají se nové soubory do projektu](media/javascript-image1.png)

Z **nový soubor** dialogového okna, vyberte **Web > soubor JS sady prázdné** nebo **Web > soubor TypeScript**. Pojmenujte ho a klikněte na tlačítko **nový**:

![Vytvoření nového souboru typescript z této šablony](media/javascript-image2.png)

## <a name="intellisense"></a>IntelliSense

Visual Studio pro Mac používá [jazyková služba JavaScriptu](/visualstudio/ide/javascript-intellisense) na poskytovat technologii IntelliSense, díky kterým inteligentní doplňování kódu, informace o parametrech a seznamech členů při psaní kódu.

Technologie intellisense jazyka JavaScript v sadě Visual Studio pro Mac může být založen na odvození typu proměnné, JSDoc nebo TypeScript deklarace.

- **Odvození typu** – typ objektu je zajištěno pomocí okolního kontext kódu. Další informace najdete v části Visual Studio na [IntelliSense podle odvození typu](/visualstudio/ide/javascript-intellisense#intellisense-based-on-type-inference).
- **JSDoc** – existují situace, kdy odvození typu neposkytuje informace o správném typu. V těchto případech lze explicitně zadat informace o typu [JSDoc](http://usejsdoc.org/about-getting-started.html) poznámky. Další informace najdete v části Visual Studio na [IntelliSense podle JSDoc](/visualstudio/ide/javascript-intellisense#intellisense-based-on-jsdoc)
- **Soubory TypeScript deklarace** – `.d.ts` soubory se používají k poskytnutí hodnot pro technologie IntelliSense jazyka JavaScript. Typy deklarované v tomto souboru mohou být použity jako typy v komentářích JSDoc. Další informace najdete v části Visual Studio na [na soubory TypeScript deklarací na základě technologie IntelliSense](/visualstudio/ide/javascript-intellisense#intellisense-based-on-typescript-declaration-files)

    ![přidává se soubor definice typescript](media/javascript-image3.png)

## <a name="see-also"></a>Viz také:

- [Technologie IntelliSense jazyka JavaScript (Visual Studio na Windows)](/visualstudio/ide/javascript-intellisense)
