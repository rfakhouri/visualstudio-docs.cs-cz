---
title: JavaScript a TypeScript ve Visual Studio 2019
ms.date: 03/27/2019
ms.technology: vs-javascript
ms.topic: conceptual
dev_langs:
- JavaScript
- TypeScript
- DHTML
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: '>= vs-2019'
ms.openlocfilehash: 3000510c6bb6079629a3df05909417593569c932
ms.sourcegitcommit: 36f5ffd6ae3215fe31837f4366158bf0d871f7a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/08/2019
ms.locfileid: "59232259"
---
# <a name="javascript-and-typescript-in-visual-studio-2019"></a>JavaScript a TypeScript ve Visual Studio 2019

## <a name="overview"></a>Přehled

Visual Studio 2019 poskytuje Rozsáhlá podpora vývoji v jazyce JavaScript, jak přímo pomocí JavaScriptu a také pomocí [programovacího jazyka TypeScript](http://www.typescriptlang.org), který byl vyvinut zajistit produktivitu a zajímavější JavaScript vývojové prostředí, zejména v případě, že vývoj projektů ve velkém měřítku. Můžete napsat kód jazyka JavaScript nebo TypeScript v sadě Visual Studio pro mnoho typů aplikací a služeb.

## <a name="javascript-language-service"></a>Služba jazyka JavaScript

Prostředí jazyka JavaScript v aplikaci Visual Studio 2019 používá stejný modul, který poskytuje podporu TypeScript. To poskytuje lepší podporu funkcí, kombinujícím a integrace okamžitě out-of-the-box.

Obnovit starší službě jazyka JavaScript je již k dispozici. Uživatelé teď mají nové JavaScript language služby out-of-the-box. Nová jazyková služba je založen výhradně na službě jazyka TypeScript, který používá statické analýzy. Umožňuje nám to poskytují lepší nástroje, takže kódu jazyka JavaScript využívat propracovanější IntelliSense podle definice typu. Tato nová služba je nenáročná a využívá méně paměti, než je starší verze služby, poskytuje lepší výkon jako škálování vašeho kódu. Vylepšili jsme také výkon služby jazyka ke zpracování větší projekty.

## <a name="typescript-support"></a>Podpora pro TypeScript

Visual Studio 2019 poskytuje několik možností pro integraci TypeScript kompilace do projektu:

* [Balíček TypeScript NuGet](https://www.nuget.org/packages/Microsoft.TypeScript.MSBuild). Při instalaci balíčku NuGet pro TypeScript 3.2 nebo vyšší do projektu bude načten odpovídající verze služby jazyka TypeScript v editoru.
* TypeScript SDK, k dispozici v instalačním programu sady Visual Studio, jakož i SDK stáhnout samostatně z ve výchozím nastavení [VS Marketplace](https://marketplace.visualstudio.com/items?itemName=TypeScriptTeam.typescript-331-vs2017).
* [Balíček npm TypeScript](https://www.npmjs.com/package/typescript). Při instalaci balíčku npm pro TypeScript 2.1 nebo vyšší do projektu bude načten odpovídající verze služby jazyka TypeScript v editoru.

Pro projekty vyvinuté v aplikaci Visual Studio 2019 doporučujeme vám používat balíčky npm a TypeScript NuGet pro větší přenositelnost napříč různými platformami a prostředí.

## <a name="projects"></a>Projekty

Javascriptové aplikace UPW se už v sadě Visual Studio 2019 nepodporují. Nejde vytvořit nebo otevřít projekty UPW v JavaScriptu (soubory s příponou *.jsproj*). Přečtěte si víc prostřednictvím naší dokumentace na [vytváření progresivní webových aplikací (PWAs)](https://docs.microsoft.com/microsoft-edge/progressive-web-apps/get-started) , která dobře fungovat na Windows.
