---
title: "Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad. | Microsoft Docs"
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
helpviewer_keywords: disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 798563e43a775ea3bb852c6603fa575c6c937943
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad.
Přečte tuto chybu:  
  
 Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad pro aktuální umístění, kde byla zastavena provádění.  
  
 Tato chybová zpráva může dojít z několika příčin:  
  
-   Může mít dosáhl zarážka v umístění, pro který není žádný zdrojový kód, při ladění jazyk, který nepodporuje zpětný překlad. Otevřete **zarážky** okně vyhledejte zarážce a odstraňte ji.  
  
-   Pokud jsou ladění skriptu, můžete mít narazit zarážku při nebyly žádné vláken v programu. Zvolte **krok** nebo **pokračovat** z **ladění** Chcete-li pokračovat, ladění, v nabídce.  
  
-   Aspekty zabezpečení mohly znemožnit ladicí program z čtení zásobníku a přístup z více vláken, zápis a další informace o kontextu programu, kterou ladíte. Toto je nejčastěji dochází, pokud jsou ladění webové aplikace a nemáte správné oprávnění pro přístup k virtuálnímu adresáři. Nastavení zabezpečení pro virtuální adresář na anonymní a zkuste to znovu.  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md) [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)