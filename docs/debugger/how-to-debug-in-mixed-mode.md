---
title: 'Postupy: ladění ve smíšeném režimu | Microsoft Docs'
ms.custom: ''
ms.date: 06/19/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b39191422eeb4c808faf858fc1ef8abb9a0a41e2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-in-mixed-mode"></a>Postupy: Ladění ve smíšeném režimu
Následující postupy popisují postup ladění spravovaná a nativní kód, také známé jako ladění ve smíšeném režimu. Existují dva scénáře pro to, v závislosti na tom, zda knihovnu DLL nebo aplikace napsané v nativním kódu:  
  
-   Volající aplikace, který volá vaše knihovna DLL je napsán v nativním kódu. V takovém případě je spravovat vaše knihovna DLL a spravovaná a nativní ladicí programy musí být povoleno ladění obě. To můžete zkontrolovat  **\<Projekt > stránky vlastností** dialogové okno. Tento postup závisí na tom, jestli spuštění ladění z projektu knihovny DLL nebo volání projekt aplikace.  
  
-   Volající aplikace, který volá vaše knihovna DLL je zapsané ve spravovaném kódu a vaše knihovna DLL je zapsán v nativním kódu.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

Pokud nemáte přístup k projektu pro volání aplikace, můžete ladit, knihovny DLL z projektu knihovny DLL. Další informace najdete v tématu [postupy: ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md). Nemusíte používat ve smíšeném k ladění právě projektu knihovny DLL.
  
### <a name="to-enable-mixed-mode-debugging-c-calling-app"></a>Pokud chcete povolit ladění ve smíšeném režimu (volání aplikace C++)  
  
1.  V **Průzkumníku**, vyberte nativnímu projektu.
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **stránky vlastností**.
  
3.  V  **\<Projekt > stránky vlastností** dialogové okno, rozbalte seznam **vlastnosti konfigurace** uzel a potom vyberte **ladění**.  
  
4.  Nastavit **ladicího programu typ** k **smíšený** nebo **automaticky**.

    ![Povolit ladění ve smíšeném režimu](../debugger/media/dbg-mixed-mode-from-native.png "povolit ladění ve smíšeném režimu")

### <a name="to-enable-mixed-mode-debugging-c-or-vb-calling-app"></a>Pokud chcete povolit ladění ve smíšeném režimu (C# nebo VB volání aplikace)  
  
1.  V **Průzkumníku**, vyberte spravovaný projekt.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **stránky vlastností**.  
  
3.  V  **\<Projekt > stránky vlastností** dialogové okno, vyberte **ladění** a pak vyberte **povolit ladění nativního kódu**

    ![Povolit ladění nativního kódu](../debugger/media/dbg-mixed-mode-from-csharp.png "povolit ladění nativního kódu")
  
## <a name="see-also"></a>Viz také  
 [Postupy: ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md)