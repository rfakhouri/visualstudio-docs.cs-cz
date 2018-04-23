---
title: 'Postupy: stránku nahoru nebo dolů v paměti | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, paging up or down in memory
- memory, paging up or down
- Disassembly window, viewing memory space
- Memory window, paging up or down in memory
ms.assetid: 50b30a68-66f6-43f8-a48b-59ce12c95471
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c87dc65bd48d47e54c4c46099c264a0c7051957
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-page-up-or-down-in-memory"></a>Postupy: O stránku nahoru nebo dolů v paměti
Při prohlížení obsah paměti v **paměti** okno nebo **zpětný překlad** můžete použít svislý posuvník přesunout nahoru nebo dolů v paměti prostor.  
  
### <a name="to-page-up-or-down-in-memory"></a>Na stránce nahoru nebo dolů v paměti  
  
1.  Na stránce dolů (přesunout vyšší adresa paměti), klikněte na tlačítko svislý posuvník posuvníku.  
  
2.  Na stránce nahoru (přesunout nižší adresa paměti), klikněte na tlačítko svislý posuvník výše jezdce.  
  
 Také si všimněte, že svislý posuvník funguje nestandardní způsobem. Adresní prostor moderní počítače je velmi velké a je snadno získat ztráty metodou úchytu posuvníku a jeho přetažením na náhodném umístění. Z tohoto důvodu úchytu je "springloaded" a vždy zůstává ve středu posuvník. V nativním kódu aplikace mohou stránku nahoru nebo dolů ale nejde o volně přejděte.  
  
 Ve spravovaných aplikacích zpětný překlad je omezený na jednu funkci a můžete posouvat normálně.  
  
 Si všimnete, že vyšší adresy se zobrazí v dolní části okna. Chcete-li zobrazit adresu vyšší, musíte přesunout dolů, není až.  
  
#### <a name="to-move-up-or-down-one-instruction"></a>Chcete-li přesunout nahoru nebo dolů o jednu instrukcí  
  
-   Klikněte na šipku v horní nebo dolní části Svislý posuvník.  
  
## <a name="see-also"></a>Viz také  
 [Okna paměti](../debugger/memory-windows.md)   
 [Postupy: použití okna zpětného překladu](../debugger/how-to-use-the-disassembly-window.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)