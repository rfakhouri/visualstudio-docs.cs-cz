---
title: Smíšený režim ladění pro x64 procesy je podporována pouze při použití rozhraní Microsoft.NET Framework 4 nebo vyšší | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 224e4de9e3a00882cb065037005b7644343262d5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>Ladění ve smíšeném režimu pro procesy x64 je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 4 nebo vyšší
Rozhraní .NET framework verze starší než 4 neposkytuje podporu pro ladění ve smíšeném režimu x64 zpracuje. To znamená, že při ladění nelze krok ze spravovaného kódu do nativního kódu nebo z nativního kódu pro spravovaný kód.  
  
### <a name="workarounds"></a>Alternativní řešení  
  
-   Aktualizujte projektu pro použití rozhraní Microsoft .NET Framework 4 nebo novější.  
  
     -nebo-  
  
     Ladění nativního a spravovaného kódu v samostatných relace ladění.  
  
     -nebo-  
  
     Ladit smíšený kód jako 32bitový proces, jak je popsáno v následujících postupech.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Chcete-li změnit platformu pro 32-bit (Visual Basic a C#)  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti**.  
  
2.  Na stránkách vlastností klikněte **zkompilovat** nebo **ladění** kartě.  
  
3.  Klikněte na tlačítko **platformy** a vyberte x86 ze seznamu platformy.  
  
     Ve výchozím nastavení vytvořit výchozí kompilátory jazyka Visual Basic a C# kód pro spuštění na libovolném procesoru. Na 64bitovém počítači spusťte tyto binární soubory jako 64bitové procesy. Pokud chcete spustit u 32-bit procesu, je nutné vybrat **Win32**, nikoli **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Chcete-li změnit platformu pro 32-bit (C/C++)  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti**.  
  
2.  Na stránkách vlastností klikněte na tlačítko **platformy** a vyberte ze seznamu platformy Win32.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   V tématu [nastavení ladění SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Viz také  
 [Ladění 64bitových aplikací](../debugger/debug-64-bit-applications.md)