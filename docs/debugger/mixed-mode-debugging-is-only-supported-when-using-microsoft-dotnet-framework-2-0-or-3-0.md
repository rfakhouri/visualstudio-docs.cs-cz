---
title: Ladění ve smíšeném režimu je podporována pouze při použití rozhraní Microsoft .NET Framework 2.0 nebo 3.0. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e27c1d8681d2a20e58ede6279f5841c4213333b6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Ladění ve smíšeném režimu je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 2.0 nebo 3.0.
Verze rozhraní Microsoft .NET Framework starší než 2.0 neposkytují podpora ladění ve smíšeném režimu 64bitové procesy. To znamená, že jste nelze krok ze spravovaného kódu do nativního kódu nebo z nativního kódu do spravovaného kódu, při ladění.  
  
 Chcete-li tento problém obejít, můžete:  
  
-   Aktualizujte projektu pro použití buď rozhraní Microsoft .NET Framework 2.0 nebo 3.0.  
  
-   Ladění nativního a spravovaného kódu v samostatných relace ladění.  
  
-   Ladit smíšený kód jako 32bitový proces, jak je popsáno v následujících postupech.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>Chcete-li změnit operační systém na 32-bit (Visual Basic a C#)  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti** v místní nabídce.  
  
2.  Na stránkách vlastností klikněte **zkompilovat** nebo **ladění** kartě.  
  
3.  Klikněte na tlačítko **platformy**a potom vyberte **x86** ze seznamu platformy.  
  
     Ve výchozím nastavení kompilátory jazyka Visual Basic a C# vytvořit kód pro spuštění na libovolném procesoru. Na 64bitovém počítači spusťte tyto binární soubory jako 64bitové procesy. Pokud chcete spustit u 32-bit procesu, je nutné vybrat **Win32**, nikoli **AnyCPU**.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>Chcete-li změnit operační systém na 32-bit (C/C++)  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti** v místní nabídce.  
  
     Na stránkách vlastností klikněte na tlačítko **platformy**a potom vyberte **Win32** ze seznamu platformy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   V tématu [nastavení ladění SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Viz také  
 [Ladění 64bitových aplikací](../debugger/debug-64-bit-applications.md)