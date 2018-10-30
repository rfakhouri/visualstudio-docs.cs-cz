---
title: 'Postupy: použití úprav v režimu pozastavení pomocí operace upravit a pokračovat | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 263e4bf4505995a4c8eccbe7c33f59115412dda5
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2018
ms.locfileid: "50219507"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Postupy: Použití úprav v režimu pozastavení pomocí operace Upravit a pokračovat
Můžete upravit a pokračovat pro úpravy kódu v režimu pozastavení a potom pokračujte bez zastavení a restartování spuštění.  
  
Omezení pomocí funkce upravit a pokračovat při ladění, naleznete v tématu [podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>Pro úpravu kódu v režimu pozastavení  
  
1.  Zadejte režimu pozastavení pomocí jedné z následujících akcí:  
  
    -   Nastavte zarážku v kódu a pak zvolte **spustit ladění** z **ladění** nabídky a vyčkat, než aplikace k zarážce.  
  
         -nebo-  
  
    -   Spustit ladění a pak vyberte **příkaz Pozastavit vše** z **ladění** nabídky.  
  
         -nebo-  
  
    -   Když dojde k výjimce, zvolte **povolit úpravy** na **Pomocníka pro výjimky**.  
  
2.  Žádné změny kódu požadované a podporované.  
  
     Další informace najdete v tématu [podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md).  
  
    > [!NOTE]
    >  Při pokusu o aby kód změnit, která není povolena funkce upravit a pokračovat, úpravy bude podtržené podle fialovou vlnovkou a úloha se zobrazí v seznamu úkolů. Nebude moct pokračovat v provádění kódu není-li vrátit změnu neplatný kód.  
  
3.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat** pokračovat provádění.  
  
     S použité úpravy do projektu se teď spustí váš kód.  
  
## <a name="see-also"></a>Viz také  
 [Podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [Upravit a pokračovat (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)