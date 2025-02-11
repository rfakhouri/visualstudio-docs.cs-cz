---
title: Ladění ve smíšeném režimu je podporováno pouze při použití rozhraní Microsoft .NET Framework 2.0 nebo 3.0. | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fc45927ad6cc1189ed1d08328b4dd362821cdcb6
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65696468"
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Ladění ve smíšeném režimu je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 2.0 nebo 3.0.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Verze rozhraní Microsoft .NET Framework starší než 2.0 se neposkytuje podporu pro pracující v kombinovaném režimu ladění 64bitových procesů. To znamená, že nelze přejdete ze spravovaného kódu do nativního kódu nebo z nativního kódu pro spravovaný kód při ladění.  
  
 Chcete-li tento problém obejít, můžete:  
  
- Aktualizujte projekt pro použití buď rozhraní Microsoft .NET Framework 2.0 nebo 3.0.  
  
- Ladění spravovaného a nativního kódu v samostatné relace ladění.  
  
- Ladit smíšený kód jako 32bitový proces, jak je popsáno v následujících postupech.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>Chcete-li změnit operační systém na 32 bitů (Visual Basic nebo C#)  
  
1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti** v místní nabídce.  
  
2. Na stránkách vlastností, klikněte na tlačítko **kompilaci** nebo **ladění** kartu.  
  
3. Klikněte na tlačítko **platformy**a pak vyberte **x86** ze seznamu platformy.  
  
     Ve výchozím nastavení kompilátory jazyků Visual Basic a C# vytvářet kód pro spuštění na jakýkoli procesor. Na 64bitovém počítači spusťte tyto binární soubory jako 64bitové procesy. Ke spuštění na 32bitový proces, musíte zvolit **Win32**, nikoli **AnyCPU**.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>Chcete-li změnit operační systém na 32 bitů (C/C++)  
  
1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti** v místní nabídce.  
  
     Na stránkách vlastností, klikněte na tlačítko **platformy**a pak vyberte **Win32** ze seznamu platformy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Zobrazit [nastavení ladění SQL](https://msdn.microsoft.com/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Viz také  
 [Ladění 64bitových aplikací](../debugger/debug-64-bit-applications.md)
