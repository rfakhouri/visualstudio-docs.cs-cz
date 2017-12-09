---
title: "Visual Studio kódu stylu předvoleb | Microsoft Docs"
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.openlocfilehash: 24470f4fdb1a75d6ebd2743b2ade72e6195842b4
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="code-style-preferences"></a>Kód stylu předvoleb

Kód stylu předvoleb lze nastavit pro projekty C# a Visual Basic otevřením **možnosti** dialogové okno z **nástroje** nabídky. Vyberte **textového editoru**, **C#** nebo **základní**, **kódu stylu**, **Obecné**. Možnosti nastavení v tomto okně platí pro místní počítač. Každá položka v seznamu se zobrazí náhled předvoleb při výběru, jak je uvedeno níže.

![Možnosti styl kódu](media/code-style-quick-actions-dialog.png)

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** pomocí rozevírací nabídky na každém řádku. Závažnost může být nastaven na **žádné**, **návrhu**, **upozornění**, nebo **chyba**, a Visual Studio budou chovat správně. Pokud chcete použít [rychlé akce](quick-actions.md) s těmito kód styly automaticky přepište kód na styl upřednostňované, ověřte, zda nastavení na jinou hodnotu než **žádné** proto ikonou žárovky ![Malé ikonou žárovky](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall") se zobrazí, pokud jsou použity styly jiný než upřednostňovaný. Tyto předvolby můžete pak můžete použít klepnutím na ikonu žárovky nebo stisknutím **Ctrl +.** Pokud je ukazatelem na příslušný řádek kódu.

Kód nastavení stylů pro rozhraní .NET můžete také spravovat pomocí [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) souboru. V takovém případě nastavení v souboru EditorConfig mají přednost před možnosti vybrané v **možnosti** dialogové okno. Soubor EditorConfig slouží k vynucení a nakonfigurovat stylu psaní kódu pro celý úložišti nebo projektu.

## <a name="see-also"></a>Viz také

[Rychlé akce](quick-actions.md)  
[Kódování nastavení konvence pro EditorConfig rozhraní .NET](../ide/editorconfig-code-style-settings-reference.md)