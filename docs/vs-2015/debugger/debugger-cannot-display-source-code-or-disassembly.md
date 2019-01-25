---
title: Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2b197785cee0250959e26726b1a81a48bb15049a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760483"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
