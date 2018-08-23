---
title: Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd21a38123894e7254bf4af6629528f8af4bf52d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670774"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad](https://docs.microsoft.com/visualstudio/debugger/debugger-cannot-display-source-code-or-disassembly).  
  
Přečte tuto chybu:  
  
 Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad pro aktuální umístění, kde vykonávání se zastavilo.  
  
 K této chybě může dojít z několika důvodů:  
  
-   Můžete narazit zarážku v umístění, pro který neexistuje žádný zdrojový kód při ladění v jazyce, který nepodporuje zpětný překlad. Otevřít **zarážky** okna, vyhledejte zarážku zase ho smažete.  
  
-   Když provádíte ladění skriptu, můžete narazit zarážky během nebyly žádná vlákna ve svém programu. Zvolte **krok** nebo **pokračovat** z **ladění** nabídky pokračovat v ladění.  
  
-   Důležité informace o zabezpečení může znemožnit ladicího programu ze zásobníku a vlákna, zápis a další informace o kontextu čtením program, který ladíte. Toto je nejčastěji dochází, pokud jsou ladění webové aplikace a nemáte správná oprávnění pro přístup k virtuálnímu adresáři. Nastavení zabezpečení pro virtuální adresář pro anonymní a zkuste to znovu.  
  
## <a name="see-also"></a>Viz také  
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)



