---
title: "Postupy: vyhledání DLL, které Program selhal v | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95ad4f9c028b9b40bf5104539a608453c9d6f9dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>Postupy: Hledání knihovny DLL, ve které program selhal.
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, vyberte v nabídce Nástroje pro nastavení importu a exportu. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 Pokud vaše aplikace, dojde k chybě při volání systémové knihovny DLL nebo kód jiného uživatele, budete muset najít na které byl aktivní knihovny DLL, když došlo k havárii. Pokud dojde k chybě v knihovně DLL mimo vlastní program, můžete identifikovat pomocí umístění **moduly** okno.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Najít kde havárie došlo k použití okna moduly  
  
1.  Poznamenejte si adresu, kde došlo k havárii.  
  
2.  Na **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **moduly**.  
  
3.  V **moduly** okně Najít **adresu** sloupce. Musíte použít posuvník k jeho zobrazení.  
  
4.  Klikněte **adresu** tlačítka v horní části Tento sloupec seřadit podle adresy knihovny DLL.  
  
5.  Kontrola seřazený seznam najít knihovnu DLL, jejichž rozsah adres obsahuje umístění havárií.  
  
6.  Podívejte se na **název** a **cesta** sloupce zobrazíte DLL název a cesta.  
  
## <a name="see-also"></a>Viz také  
 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md)   
 [Postupy: použití okna moduly](../debugger/how-to-use-the-modules-window.md)