---
title: Spustitelný pro ladění, dialogové okno relace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.exefordebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d6bc004ac9d450e0f5ea358d16bb25ab6cabecf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018747"
---
# <a name="executable-for-debugging-session-dialog-box"></a>Dialogové okno Spustitelný soubor pro relaci ladění

Toto dialogové okno se zobrazí při pokusu o ladění knihovny DLL pro kterou žádná spustitelný soubor je určen. Visual Studio nelze spustit knihovnu DLL přímo. Místo toho Visual Studio spustí zadaný spustitelný soubor. Když je volána metodou spustitelný soubor můžete ladit knihovnu DLL.  
  
 **Název spustitelného souboru**  
 Zadejte název cesty do spustitelného souboru, který volá knihovnu DLL, který ladíte.  
  
 **Adresa URL, kde projektu lze získat přístup (pouze Server ATL)**  
 Pokud ladíte knihovnu ATL DLL serveru, zadejte adresu URL, kde lze nalézt projektu.  
  
 Po zadání, tato nastavení jsou uložena v projektu stránky vlastností, takže nebude nutné zadávat znovu při další relace ladění. Pokud potřebujete změnit nastavení, můžete otevřít stránky vlastností a změňte hodnoty. Další informace o zadání spustitelný soubor pro relaci ladění, naleznete v tématu [ladění knihoven DLL](../debugger/how-to-debug-from-a-dll-project.md).  
  
## <a name="see-also"></a>Viz také

 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)