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
ms.openlocfilehash: 41b93ae19afd54b6e22458d1ba12029d5bb93cf3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62849957"
---
# <a name="executable-for-debugging-session-dialog-box"></a>Dialogové okno Spustitelný soubor pro relaci ladění

Toto dialogové okno se zobrazí při pokusu o ladění knihovny DLL pro kterou žádná spustitelný soubor je určen. Visual Studio nelze spustit knihovnu DLL přímo. Místo toho Visual Studio spustí zadaný spustitelný soubor. Když je volána metodou spustitelný soubor můžete ladit knihovnu DLL.

 **Název spustitelného souboru** zadejte název cesty do spustitelného souboru, který volá knihovnu DLL, který ladíte.

 **Adresa URL, kde projektu lze získat přístup (pouze Server ATL)** Pokud ladíte knihovnu ATL DLL serveru, zadejte adresu URL, kde lze nalézt projektu.

 Po zadání, tato nastavení jsou uložena v projektu stránky vlastností, takže nebude nutné zadávat znovu při další relace ladění. Pokud potřebujete změnit nastavení, můžete otevřít stránky vlastností a změňte hodnoty. Další informace o zadání spustitelný soubor pro relaci ladění, naleznete v tématu [ladění knihoven DLL](../debugger/how-to-debug-from-a-dll-project.md).

## <a name="see-also"></a>Viz také

- [Ladění v sadě Visual Studio](../debugger/index.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)