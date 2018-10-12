---
title: 'Postupy: ladění ve smíšeném režimu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 06/19/2018
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 8a08cf3cf95073d06c1dfa350f2de86bf72837c5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182673"
---
# <a name="how-to-debug-in-mixed-mode"></a>Postupy: ladění ve smíšeném režimu
Následující postupy popisují, jak povolit ladění spravovaného a nativního kódu společně, označované také jako pracující v kombinovaném režimu ladění. Existují dva scénáře ladění ve smíšeném režimu:  
  
- Aplikace, který volá knihovnu DLL je napsaná v nativním kódu a spravované knihovny DLL. 
  
- Aplikace, který volá knihovnu DLL je zapsána ve spravovaném kódu a knihovny DLL je v nativním kódu. Kurz vás provede tento scénář podrobněji, najdete v tématu [ladění spravovaného a nativního kódu](../debugger/how-to-debug-managed-and-native-code.md).
   
Můžete povolit spravované i nativní ladicí programy ve volání aplikace projektu **vlastnost** stránky. Nastavení se liší mezi nativními a spravovanými aplikacemi. 

Pokud nemáte přístup k projektu volání aplikace, můžete ladit knihovnu DLL z projektu knihovny DLL. Kombinovaný režim ladění projektu knihovny DLL nepotřebujete. Další informace najdete v tématu [postupy: ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md). 

> [!NOTE]
> Dialogová okna a příkazy, které vidíte mohou lišit od těch v tomto článku, v závislosti na edici nebo nastavení sady Visual Studio. Chcete-li změnit nastavení, zvolte **nástroje** > **nastavení importu a exportu**. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="enable-mixed-mode-debugging-for-a-native-calling-app"></a>Povolit ladění ve smíšeném režimu pro nativní volající aplikace  
  
1. Vyberte projekt C++ v **Průzkumníka řešení** a klikněte na tlačítko **vlastnosti** ikonu, stiskněte klávesu **Alt**+**Enter**, nebo Klikněte pravým tlačítkem a zvolte **vlastnosti**.
   
1. V  **\<Projekt > stránky vlastností** dialogového okna rozbalte **vlastnosti konfigurace**a pak vyberte **ladění**.  
   
1. Nastavte **typ ladicího programu** k **smíšené** nebo **automaticky**.
   
1. Vyberte **OK**.
   
   ![Povolit ladění ve smíšeném režimu](../debugger/media/dbg-mixed-mode-from-native.png "povolit ladění ve smíšeném režimu")

## <a name="enable-mixed-mode-debugging-for-a-managed-calling-app"></a>Povolit ladění ve smíšeném režimu pro spravovanou aplikaci volání  
  
1. Vyberte projekt C# nebo Visual Basic v **Průzkumníka řešení** a vyberte **vlastnosti** ikonu, stiskněte klávesu **Alt**+**Enter**, nebo klikněte pravým tlačítkem a zvolte **vlastnosti**.
   
1. Vyberte **ladění** kartu a potom vyberte **povolit ladění nativního kódu**.
   
1. Použití **souboru** > **uložit vybrané položky** nebo **Ctrl + S** uložte změny.

   ![Povolit ladění nativního kódu](../debugger/media/dbg-mixed-mode-from-csharp.png "povolit ladění nativního kódu")
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md)