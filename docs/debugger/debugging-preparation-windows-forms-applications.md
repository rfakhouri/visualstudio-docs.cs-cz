---
title: Příprava na ladění aplikací pro Windows Forms | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging Windows applications
- Windows applications, debugging
- debugging [Visual Studio], Windows applications
- debugging [C#], Windows applications
- debugging [Visual Basic], Windows applications
ms.assetid: 7092ee7f-8378-4def-aef8-1695bd97cf14
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5cc06e33b3549bda9bdc9fe04073ca4cf0d9e9a5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851779"
---
# <a name="debugging-preparation-windows-forms-applications"></a>Příprava ladění: Formulářová aplikace Windows
Šablona projektu Windows Forms vytvoří aplikace modelu Windows Forms. Ladění tohoto typu aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je jednoduché. Další informace najdete v tématu [vytvoření projektu aplikace Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/42wc9kk5(v=vs.100)).

 Při vytváření projektu Windows Forms pomocí šablony projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky vytvoří požadované nastavení konfigurace Debug a Release. V případě potřeby můžete tato nastavení změnit. Tato nastavení lze změnit v  **\<název projektu > stránky vlastností** dialogové okno (**Můj projekt** v jazyce Visual Basic).

 Další informace najdete v tématu [doporučené nastavení vlastností](../debugger/managed-debugging-recommended-property-settings.md).

 Následující tabulka obsahuje jeden další vlastnost doporučené nastavení.

### <a name="configuration-properties-in-debug-tab"></a>Vlastnosti konfigurace na kartě ladění

|**Název vlastnosti**|**Nastavení**|
|-----------------------|-----------------|
|**Spustit akci**|– Nastavte na **spustit projekt** většinu času. Nastavte na **externí program Start** Pokud budete chtít spustit jiné spustitelný soubor při spuštění ladění (většinou pro ladění knihoven DLL).|

 Můžete ladit aplikace Windows Forms z uvnitř [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nebo připojením k již běžícímu aplikace. Další informace o připojení najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>Chcete-li ladit C#, F#, nebo aplikaci Windows Forms jazyka Visual Basic

1. Otevřete projekt v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

2. Podle potřeby vytvořte zarážky.

    Protože aplikace Windows Forms jsou založené na událostech, vaše zarážky přejde do kódu obslužné rutiny události nebo do metody volané kódem obslužné rutiny události. Typické události, ve které chcete umístit zarážky zahrnují:

   1. Události související s ovládacím prvkem, jako je například klikněte na Enter, atd.

   2. Události související s aplikací při spuštění a vypnutí, jako je zatížení, aktivováno atd.

   3. Fokus a události ověřování.

      Další informace najdete v tématu [vytváření obslužných rutin událostí ve Windows Forms](/dotnet/framework/winforms/creating-event-handlers-in-windows-forms).

3. Na **ladění** nabídky, klikněte na tlačítko **Start**.

4. Ladění pomocí technik popsaných v [nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md).

## <a name="see-also"></a>Viz také
- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
- [Typy projektů jazyka C#, F# a Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
- [Postupy: Nastavení konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md)
- [Nastavení projektu pro konfiguraci ladění jazyka C#](../debugger/project-settings-for-csharp-debug-configurations.md)
- [Nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)
- [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Windows Forms](/dotnet/framework/winforms/index)