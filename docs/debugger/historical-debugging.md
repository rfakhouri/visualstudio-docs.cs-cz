---
title: Historické ladění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f8019d9363b2a599ac4115c3d6d25a465a3bd0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="historical-debugging"></a>Historické ladění
Historické ladění je režim ladění, která závisí na informacích shromažďovaných IntelliTrace. Umožňuje přesunout zpátky a předávat prostřednictvím spuštění vaší aplikace a zkontrolovat stav.  
  
 Můžete vytvořit IntelliTrace ve Visual Studio Enterprise edition (ale ne edice Professional nebo komunity).  
  
## <a name="why-use-historical-debugging"></a>Proč používat historické ladění?  
 Nastavení zarážek najít chyby může být místo hit-or-miss záležitost. Nastavte zarážky blízko místa ve vašem kódu kde podezření chyb jako a pak spusťte aplikaci v Doufáme, že vaší zarážce získá stiskněte klávesu a že na místě, kde provádění dělí může odhalit zdroj chyb a ladicí program. Pokud ne, budete muset zkuste nastavit zarážky někde jinde v kódu a znovu spusťte ladicí program, provádění testovací kroky opakovaně, dokud narazíte potíže.  
  
 ![nastavení boru přerušení](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 Můžete použít IntelliTrace a historické ladění přemístit kolem ve vaší aplikaci a zkontrolovat stav (zásobník volání a místní proměnné) bez nutnosti nastavit zarážky, znovu spusťte ladění a opakujte kroky testu. To můžete ušetřit mnoho času, zejména při chybě nachází hloubky ve scénáři testu, která trvá dlouhou dobu spuštění.  
  
## <a name="how-do-i-start-using-historical-debugging"></a>Jak spustit pomocí historické ladění?  
 Ve výchozím nastavení zapnutý IntelliTrace. Všechny, které musíte udělat je, rozhodněte, které události a volání funkce jsou vás zajímají, a jestli chcete zobrazit snímky vaší úplném stavu aplikace. Další informace o definování, co chcete hledat najdete v tématu [funkce IntelliTrace](../debugger/intellitrace-features.md).  

 - Snímky s historické ladění najdete v tématu [zobrazit snímky pomocí zpětný krok IntelliTrace](../debugger/how-to-use-intellitrace-step-back.md)
 - Zjistěte, jak zkontrolovat proměnné a přejděte kód, najdete v tématu [zkontrolovat vaší aplikace pomocí historické ladění](../debugger/historical-debugging-inspect-app.md)
 - Další informace o ladění pomocí událostí IntelliTrace, najdete v části [návod: použití IntelliTrace](../debugger/walkthrough-using-intellitrace.md).