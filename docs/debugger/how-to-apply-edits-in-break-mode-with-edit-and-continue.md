---
title: "Postupy: použití úprav v režimu pozastavení pomocí operace upravit a pokračovat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.variables.failededit
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
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 54fb069f5328dd9bc7cabab16c0688109312dfd1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Postupy: Použití úprav v režimu pozastavení pomocí operace Upravit a pokračovat
Úprava kódu v režimu pozastavení a pokračujte bez zastavení a restartování provádění můžete upravit a pokračovat.  
  
Omezení použití upravit a pokračovat při ladění, najdete v části [podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>Chcete-li upravit kód v režimu pozastavení  
  
1.  Zadejte režim pozastavení jedním z následujících akcí:  
  
    -   Nastavte zarážky v kódu, a potom vyberte **spustit ladění** z **ladění** nabídky a počkejte průchodu zarážkou aplikace.  
  
         -nebo-  
  
    -   Spuštění ladění a potom vyberte **přerušení všech** z **ladění** nabídky.  
  
         -nebo-  
  
    -   Když dojde k výjimce, zvolte **povolit úpravy** na**Pomocníka pro výjimky**.  
  
2.  Proveďte požadované změny kódu požadované a podporované.  
  
     Další informace najdete v tématu [podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md).  
  
    > [!NOTE]
    >  Pokud se pokusíte aby kódu změňte, která není povolena upravit a pokračovat, úpravy bude podtržené fialové vlnovkami čára a úlohy se zobrazí v seznamu úloh. Nebudete moci pokračovat v provádění kódu Pokud vrátit změnu neplatný kód.  
  
3.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat** Chcete-li pokračovat v provádění.  
  
     Váš kód teď provede úpravy dokončíte použité součástí projektu.  
  
## <a name="see-also"></a>Viz také  
 [Podporované změny kódu (C# a Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [Upravit a pokračovat (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)