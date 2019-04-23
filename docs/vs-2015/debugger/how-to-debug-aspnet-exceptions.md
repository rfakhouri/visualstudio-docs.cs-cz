---
title: 'Postupy: Ladění výjimek ASP.NET | Dokumentace Microsoftu'
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
- debugging [Visual Studio], ASP.NET exceptions
- ASP.NET, exceptions
- exceptions, ASP.NET
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1ccd8c399bd92bd98307d44aff913c30390033c7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083709"
---
# <a name="how-to-debug-aspnet-exceptions"></a>Postupy: Ladění výjimek ASP.NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Výjimky ladění jsou důležitou součástí vývoje robustní [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikace. Obecné informace o tom, jak ladit výjimky je v [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md).  
  
 Chcete-li ladit neošetřené [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] výjimky, ujistěte se, že nich ladicí program zastavuje. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Runtime obsahuje obslužnou rutinu výjimky nejvyšší úrovně. Proto se ladicí program nikdy nezastaví na neošetřené výjimce ve výchozím nastavení. Pokud chcete přerušit do ladicího programu, pokud je vyvolána výjimka, musíte vybrat **přerušit, když výjimka je: Vyvolána** nastavení pro tuto specifickou výjimku v **výjimky** dialogové okno.  
  
 Pokud jste povolili funkce pouze můj kód, **přerušit, když výjimka je: Vyvolána** nezpůsobí okamžité přerušení, pokud je vyvolána výjimka v metodě rozhraní .NET Framework nebo jiném kódu systému ladicí program. Místo toho provádění pokračuje, dokud ladicí program narazí na nesystémové kódu, a to naruší. V důsledku toho není nutné krokovat kód systému, pokud dojde k výjimce.  
  
 Pouze můj kód poskytuje další možnost, která může být ještě užitečnější: **Přerušit, když výjimka je: Uživatelem neošetřené**. Pokud vyberete toto nastavení se pro výjimku, ladicí program přeruší provádění v uživatelském kódu, ale pouze v případě, výjimka není odchycena a zpracována uživatelským kódem. Toto nastavení Neguje působení na nejvyšší úrovni [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] obslužná rutina výjimky, protože tato obslužná rutina v neuživatelském kódu.  
  
### <a name="to-enable-debugging-of-aspnet-exceptions-with-just-my-code"></a>Pokud chcete povolit ladění výjimek ASP.NET s jen můj kód  
  
1. Na **ladění** nabídky, klikněte na tlačítko **výjimky**.  
  
     **Výjimky** zobrazí se dialogové okno.  
  
2. Na **výjimky modulu Common Language Runtime** řádek, vyberte **vyvolání** nebo **uživatelem neošetřené**.  
  
     Použít **uživatelem neošetřené** nastavení **pouze můj kód** musí být povolené...  
  
### <a name="to-use-best-practices-for-aspnet-exception-handling"></a>Použití doporučených postupů pro zpracování výjimek technologie ASP.NET  
  
- Místo `try … catch` okolo kódu, který může vyvolat výjimky, které lze předvídat a vědět, jak zpracovat. Například pokud aplikace volá do webové služby XML nebo přímo do systému SQL Server, tento kód by měl být v **try... catch** blokuje, protože existuje množství výjimek, které se mohou vyskytnout.
