---
title: 'Postupy: Kontrola systémového kódu po výjimce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2914aab911d3c700b38c58eac009b2e21e94420e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-examine-system-code-after-an-exception"></a>Postupy: Kontrola systémového kódu po výjimce
Když dojde k výjimce, můžete chtít Kontrola kódu uvnitř volání systému a zjistěte příčinu výjimku. Následující postup vysvětluje, jak to provést, pokud nemáte symboly načten pro kód systému nebo pokud je povoleno pouze můj kód.  
  
### <a name="to-examine-system-code-following-an-exception"></a>Chcete-li kontrola systémového kódu po výjimce  
  
1.  V **zásobníkem volání** okna, klikněte pravým tlačítkem, poté klikněte na tlačítko **zobrazit externí kód**.  
  
     Pokud pouze můj kód není povolena, tato možnost není k dispozici v místní nabídce a ve výchozím nastavení se zobrazí kód systému.  
  
2.  Klikněte pravým tlačítkem na externí kód rámců, které se teď zobrazují v **zásobníkem volání** okno.  
  
3.  Přejděte na příkaz **zatížení symboly z** a pak klikněte na **servery symbolů Microsoft**.  
  
    1.  Pokud je povoleno pouze můj kód, zobrazí se dialogové okno. Se stavy, že pouze můj kód teď byla zakázána. To je nezbytné pro zanoříte se do systémová volání.  
  
    2.  **Stahování veřejné symboly** zobrazí se dialogové okno. Při stahování dokončení zmizí.  
  
4.  Nyní můžete zkontrolovat kód systému **zásobníkem volání** okno a windows. Například poklepáním na rámce zásobníku volání zobrazíte kód v zdroj nebo **zpětný překlad** okno.  
  
## <a name="see-also"></a>Viz také  
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)