---
title: "Příprava na ladění: Formulářová aplikace Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 873b7dd10a2e39aa795626bc7d387df7017740d8
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/13/2017
---
# <a name="debugging-preparation-windows-forms-applications"></a>Příprava na ladění: Formulářová aplikace Windows
Šablona projektu Windows Forms vytvoří aplikaci Windows Forms. Ladění tento typ aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je jednoduché. Další informace najdete v tématu [vytváření projekt aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Při vytváření projektu Windows Forms pomocí šablony projektu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky vytvoří požadované nastavení pro konfiguraci ladění a vydání. V případě potřeby můžete změnit tato nastavení. Tato nastavení lze změnit v  **\<název projektu > stránky vlastností** dialogové okno (**Můj projekt** v jazyce Visual Basic).  
  
 Další informace najdete v tématu [doporučené nastavení vlastností](../debugger/managed-debugging-recommended-property-settings.md).  
  
 Následující tabulka zobrazuje jeden další vlastnosti doporučené nastavení.  
  
### <a name="configuration-properties-in-debug-tab"></a>Vlastnosti konfigurace v karty ladění  
  
|**Název vlastnosti**|**Nastavení**|  
|-----------------------|-----------------|  
|**Zahájení**|– Nastavte na **spuštění projektu** většinu času. Nastavte na **počáteční vnějšímu programu** Pokud chcete spustit spustitelný soubor jiného při prvním spuštění ladění (obvykle pro ladění knihoven DLL).|  
  
 Můžete ladit aplikace Windows Forms z uvnitř [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nebo se připojuje k již běžící aplikaci. Další informace o připojení najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>Chcete-li ladit aplikace C#, F # nebo Visual Basic Windows Forms  
  
1.  Otevřete projekt ve [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
2.  Vytvořte zarážky podle potřeby.  
  
     Protože aplikace Windows Forms založeného na událostech, bude vaše zarážky přejděte do kód obslužné rutiny události nebo do metody volá kód obslužné rutiny události. Typické události, do níž umístíte zarážky zahrnují:  
  
    1.  Události související s ovládacím prvkem, například klikněte na, zadejte atd.  
  
    2.  Události související s aplikací spuštění a vypnutí, například zatížení, aktivované atd.  
  
    3.  Události ověření a fokus.  
  
     Další informace najdete v tématu [vytváření obslužných rutin událostí v systému Windows Forms](/dotnet/framework/winforms/creating-event-handlers-in-windows-forms).  
  
3.  Na **ladění** nabídky, klikněte na tlačítko **spustit**.  
  
4.  Ladění pomocí technik popsaných v [základy ladicího programu](../debugger/debugger-basics.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Postupy: Konfigurace sady ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Konfigurace ladění nastavení projektu pro jazyk C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Nastavení projektu jazyka Visual Basic konfiguraci ladění](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](/dotnet/framework/winforms/index)