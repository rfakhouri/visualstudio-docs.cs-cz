---
title: "Styly a rychlé akce kódu | Microsoft Docs"
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 25bb9d99-aeff-4053-925d-2177f5e79574
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.openlocfilehash: d42bb9165748b7282aa42f062b545add62ad1c93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="code-styles-and-quick-actions"></a>Styly kódu a rychlé akce
Kód stylu předvoleb lze nastavit pro projekty C# a Visual Basic otevřením **nástroje > Možnosti** okna a potom vyberete **textový Editor > C# / Základní > kódu stylu > Obecné**.  Možnosti nastavení v tomto okně platí pro místní počítač.  Každá položka v seznamu se zobrazí náhled předvoleb při výběru, jak je uvedeno níže.

![Možnosti styl kódu](media/code-style-quick-actions-dialog.png)

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** pomocí rozevírací nabídky na každém řádku.  Závažnost může být nastaven na **žádné**, **návrhu**, **upozornění**, nebo **chyba**, a Visual Studio budou chovat správně.  Pokud chcete použít [rychlé akce](quick-actions.md) s těmito kód styly automaticky přepište kód na styl upřednostňované, ověřte, zda nastavení na jinou hodnotu než **žádné** proto ikonou žárovky ![Malé ikonou žárovky](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall") se zobrazí, pokud jsou použity styly jiný než upřednostňovaný.  Tyto předvolby můžete pak můžete použít klepnutím na ikonu žárovky nebo stisknutím **Ctrl +.** Pokud je ukazatelem na příslušný řádek kódu.

Kód nastavení stylů pro rozhraní .NET můžete také spravovat pomocí [EditorConfig](editorconfig-code-style-settings-reference.md) souboru.  V takovém případě bude nastavení vybraná v okně Možnosti nastavení záložní volby se souborem EditorConfig trvá prioritu.  Tento soubor můžete použít k vynucení a konfiguraci stylu psaní kódu pro celý úložišti nebo tým.

## <a name="see-also"></a>Viz také
* [Rychlé akce](quick-actions.md)