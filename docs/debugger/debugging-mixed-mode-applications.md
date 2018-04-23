---
title: Ladění ve smíšeném režimu aplikací | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging, property evaluation
- Call Stack window
- mixed-mode debugging
- Call Stack window, mixed-mode debugging
- debugging managed code, mixed code
- mixed-mode debugging, call stack
ms.assetid: 60e34477-ae4e-48c7-9093-3e37f72e1bc3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0564a1e4a03d0b2d72298f0467e6cd1a91cdab9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-mixed-mode-applications"></a>Ladění aplikací ve smíšeném režimu
Aplikace pracující v kombinovaném režimu je libovolná aplikace, která kombinuje nativní kód (jazyk C++) se spravovaným kódem (například jazyk Visual Basic, Visual C# nebo C++, který běží na modulu CLR). Ladění aplikací ve smíšeném režimu je z velké části transparentní v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]; není příliš odlišný od ladění aplikace výhradním režimu. Existuje však několik důležitých informací.  
  
## <a name="enable-c-edit-and-continue-in-mixed-mode-debugging"></a>Povolení příkazů Edit a Continue jazyka C++ v kombinovaném režimu ladění  

Chcete-li upravit a pokračovat v c++, najdete v části [povolení a zakázání upravit a pokračovat](../debugger/how-to-enable-and-disable-edit-and-continue.md).

> [!NOTE]
> Pokud chcete používat příkazy Edit a Continue (Upravit a pokračovat) jazyka C++ v sadě Visual Studio 2013, budete muset přejít na starší verzi modulu pro ladění. V tématu [přepnutí na režim kompatibility spravované v sadě Visual Studio 2013](http://blogs.msdn.com/b/visualstudioalm/archive/2013/10/16/switching-to-managed-compatibility-mode-in-visual-studio-2013.aspx) na blogu Správa životního cyklu aplikací společnosti Microsoft.  
  
## <a name="property-evaluation-in-mixed-mode-applications"></a>Vyhodnocení vlastnosti v aplikacích pracujících v kombinovaném režimu  
 Vyhodnocení vlastností ladicím programem je v aplikaci pracující v kombinovaném režimu náročná operace. V důsledku toho se operace ladění, jako je například krokování, mohou zdát pomalé. Další informace najdete v tématu [krokování](http://msdn.microsoft.com/en-us/8791dac9-64d1-4bb9-b59e-8d59af1833f9). Pokud se při ladění v kombinovaném režimu setkáváte s nízkým výkonem, lze vyhodnocení vlastností vypnout v oknech ladicího programu.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
#### <a name="to-turn-off-property-evaluation"></a>Chcete-li vypnout vyhodnocení vlastností  
  
1.  Na **nástroje** nabídky, zvolte **možnosti**.  
  
2.  V **možnosti** dialogové okno, otevřete **ladění** složky a vyberte **Obecné** kategorie.  
  
3.  Vymazat **povolit vyhodnocení vlastnosti a jiná volání funkce implicitní** zaškrtávací políčko.  
  
 Vzhledem k tomu, že se nativní a spravované zásobníky volání liší, ladicí program nemůže vždy pro smíšený kód stanovit úplný zásobník volání. Když nativní kód volá spravovaný kód, lze zaznamenat některé nesrovnalosti. Další informace najdete v tématu [smíšený kód a chybějící informace v okně zásobník volání](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)