---
title: Kombinovaný režim ladění pro x64 procesy se podporuje jenom při použití Microsoft.NET Framework 4 nebo vyšší | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e974269cccb65db66ee59735f7acc5de494e2106
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697836"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>Ladění ve smíšeném režimu pro procesy x64 je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 4 nebo vyšší
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Rozhraní .NET Framework verze nižší než 4 se neposkytuje podporu pro ladění ve smíšeném režimu x64 zpracovává. To znamená, že nelze krokovat ze spravovaného kódu do nativního kódu nebo z nativního kódu pro spravovaný kód při ladění.  
  
### <a name="workarounds"></a>Alternativní řešení  
  
- Aktualizujte projekt pro použití rozhraní Microsoft .NET Framework 4 nebo novější.  
  
     – nebo –  
  
     Ladění spravovaného a nativního kódu v samostatné relace ladění.  
  
     – nebo –  
  
     Ladit smíšený kód jako 32bitový proces, jak je popsáno v následujících postupech.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Chcete-li změnit platformu na 32 bitů (Visual Basic nebo C#)  
  
1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti**.  
  
2. Na stránkách vlastností, klikněte na tlačítko **kompilaci** nebo **ladění** kartu.  
  
3. Klikněte na tlačítko **platformy** a vyberte x86 ze seznamu platformy.  
  
     Ve výchozím nastavení výchozí kompilátory jazyka Visual Basic a C# vytvářet kód pro spuštění na jakýkoli procesor. Na 64bitovém počítači spusťte tyto binární soubory jako 64bitové procesy. Ke spuštění na 32bitový proces, musíte zvolit **Win32**, nikoli **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Chcete-li změnit platformu na 32 bitů (C/C++)  
  
1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti**.  
  
2. Na stránkách vlastností, klikněte na tlačítko **platformy** a vyberte ze seznamu platformy Win32.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Zobrazit [nastavení ladění SQL](https://msdn.microsoft.com/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Viz také  
 [Ladění 64bitových aplikací](../debugger/debug-64-bit-applications.md)
