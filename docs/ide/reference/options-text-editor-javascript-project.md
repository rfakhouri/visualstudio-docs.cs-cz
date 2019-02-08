---
title: Možnosti, textový Editor, JavaScript, projektu
ms.date: 1/15/2019
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Project.General
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Project
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Project.General
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Project
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 09ed64d6bffaa4453c3294229ee48fd0a065eb74
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936743"
---
# <a name="options-text-editor-javascript-project"></a>Možnosti, textový Editor, JavaScript, projektu

Použití **projektu** stránku **možnosti** dialogové okno k zadání možnosti projektů jazyka JavaScript v editoru kódu. Pro přístup k této stránce, na panelu nabídek zvolte **nástroje** > **možnosti**a potom rozbalte **textový Editor** > **JavaScript**  >  **Projektu**.

## <a name="project-analysis-options"></a>Možnosti analýzy projektů

Tyto možnosti určíte, jak editor analyzuje projekty, zprávy diagnostiky a navrhne vylepšení. Vyberte nebo zrušte zaškrtnutí možností, které určují, jak editor zpracovává tyto situace.

### <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

- **Analyzujte jen projekty, které obsahují soubory otevřené v editoru**
- **Oznamovat diagnostiku jenom pro soubory otevřené v editoru**
- **Navrhnout možných zlepšení, které nejsou opravy**

## <a name="virtual-projects-in-solution-explorer"></a>Virtuální projekty v Průzkumníkovi řešení

Tyto možnosti umožňují vybrat, zda zobrazení virtuální projekty, když řešení je buď načtena nebo není načtený.

## <a name="compile-on-save"></a>Zkompilovat při uložení

Tyto možnosti určují, zda jsou automaticky zkompilovány soubory TypeScript, které nejsou součástí projektu. Zaškrtněte políčko a pak zvolte typ generování kódu použití.

### <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

- **Použít generování kódu AMD u modulů, které nejsou součástí projektu**
- **Použít generování kódu CommonJS u modulů, které nejsou součástí projektu**
- **Použít generování kódu UMD u modulů, které nejsou součástí projektu**
- **Použít generování kódu systému pro moduly, které nejsou součástí projektu**
- **Použít generování kódu ES2015 u modulů, které nejsou součástí projektu**

## <a name="ecmascript-version-for-files-that-are-not-part-of-a-project"></a>Verze ECMAScript pro soubory, které nejsou součástí projektu

Tyto možnosti vám umožní vybrat verze ECMAScript pro soubory, které nejsou součástí projektu. Můžete si vybrat mezi **ECMAScript 3**, **ECMAScript 5**, nebo **ECMAScript 6**.

## <a name="jsx-emit-for-tsx-files-that-are-not-part-of-a-project"></a>JSX Emit pro soubory TSX, které nejsou součástí projektu

Tyto možnosti určují, jak editor zpracovává soubory TypeScript, které nejsou součástí projektu.

### <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

|Možnost|Popis|
|------------|-----------------|
|**Rozhraní react**|Pokud je vybraná tato možnost, vysílá editoru kódu *js* příponu souboru.|
|**Preserve**|Pokud je vybraná tato možnost, Editor kódu udržuje JSX v rámci výstupu a generuje *.jsx, které jsou* příponu souboru.|

## <a name="see-also"></a>Viz také:

- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)