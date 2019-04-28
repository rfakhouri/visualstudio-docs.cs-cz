---
title: Možnosti, textový Editor, XML, různé
ms.date: 10/29/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Miscellaneous
ms.assetid: b6538cbe-badd-4313-a1fb-39e906736bbe
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d3421580251a6a871adba311fd609e881e088ebd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969212"
---
# <a name="options-text-editor-xml-miscellaneous"></a>Možnosti, textový Editor, XML, různé

Použití **různé** stránka Možnosti, chcete-li změnit nastavení automatického doplňování spolu se schématem pro Editor XML. Chcete-li získat přístup k různé možnosti XML, zvolte **nástroje** > **možnosti** > **textový Editor** > **XML**a klikněte na tlačítko **různé**.

## <a name="auto-insert"></a>Automatické vkládání

**Zavřít značky**

Textový editor přidá zavřít značky při vytváření elementů XML. Pokud je vybrána počáteční značky elementu, editor vloží odpovídající uzavírací značka, včetně odpovídající Předpona oboru názvů. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto.

**Uvozovky atributu**

Při vytváření atributy ve formátu XML, editor vloží `="` a `"` znaků a pozice blikajícího kurzoru (**^**) v uvozovkách. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto.

**Deklarace Namespace**

Editor automaticky vloží deklarace oboru názvů, bez ohledu na to se v případě potřeby zapíná. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto.

**Jiné značky (komentáře, CDATA)**

Komentáře, CDATA, DOCTYPE, pokyny pro zpracování a jiný kód je autocompleted. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto.

## <a name="network"></a>Síť

**Automaticky stahovat specifikace DTD a schémata**

Schémata a definice typu dokumentu (DTD) se automaticky stáhnou z umístění protokolu HTTP. Tato funkce používá System.Net s detekcí autoproxy serveru povolené. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto.

## <a name="outlining"></a>Sbalování

**Po otevření souborů vstoupit do režimu sbalování**

Při otevření souboru se změní na funkci sbalování. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto.

## <a name="caching"></a>Ukládání do mezipaměti

**Schémata**

Určuje umístění mezipaměti schémat. **Procházet** tlačítko otevře v novém okně aktuální umístění mezipaměti schémat. Výchozí umístění je *%VsInstallDir%\xml\Schemas*.

## <a name="see-also"></a>Viz také:

- [Možnosti XML – formátování](options-text-editor-xml-formatting.md)
- [Nástroje XML v sadě Visual Studio](../../xml-tools/xml-tools-in-visual-studio.md)