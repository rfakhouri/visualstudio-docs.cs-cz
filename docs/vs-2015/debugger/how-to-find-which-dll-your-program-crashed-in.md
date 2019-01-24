---
title: 'Postupy: Hledání knihovny DLL které Program selhal v | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fcb5126d5281a62c9af55ba9e4283df4e1c3819c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54769941"
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>Postupy: Hledání knihovny DLL které Program selhal v
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

POZNÁMKA:]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte nastavení importu a exportu v nabídce Nástroje. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Pokud vaše aplikace dojde k chybě během volání systémové knihovny DLL nebo kód někoho jiného, budete muset najít který byl aktivní knihovny DLL, kdy došlo k selhání. Pokud dojde k chybovému ukončení v knihovně DLL mimo svůj program, můžete určit pomocí umístění **moduly** okna.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Najde, pro které selhání došlo k použití okna moduly  
  
1.  Poznamenejte si adresu, kde došlo k selhání.  
  
2.  Na **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **moduly**.  
  
3.  V **moduly** okně Najít **adresu** sloupce. Budete muset použít posuvník a prohlédněte si ho.  
  
4.  Klikněte na tlačítko **adresu** tlačítko v horní části Tento sloupec seřadit podle adresy knihovny DLL.  
  
5.  Kontrola seřazeného seznamu k nalezení knihovny DLL, jejichž rozsah adres obsahuje umístění při selhání.  
  
6.  Podívejte se na **název** a **cesta** sloupce, které chcete zobrazit název knihovny DLL a cestu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Ladění nativních knihoven DLL](../debugger/how-to-debug-native-dlls.md)   
 [Postupy: Použití okna Moduly](../debugger/how-to-use-the-modules-window.md)
