---
title: 'Postupy: zákaz procesu hostování | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47264ef7f1a6a2bd1a4ad3da59f53836f9ebb902
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-disable-the-hosting-process"></a>Postupy: zákaz procesu hostování
Je-li povolen hostitelský proces, mohou být volání určitých rozhraní API ovlivněna. V těchto případech je pro vrácení správných výsledků nutné hostitelský proces zakázat.  
  
### <a name="to-disable-the-hosting-process"></a>Zakázání hostitelského procesu  
  
1.  Otevřete projekt spustitelné aplikace v aplikaci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Projekty, které nevytváří spustitelné soubory (například knihovny tříd nebo projekty služeb) tuto možnost nemají.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
3.  Klikněte **ladění** kartě.  
  
4.  Vymazat **povolit sady Visual Studio proces hostování** zaškrtávací políčko.  
  
 Je-li hostitelský proces zakázán, nebudou k dispozici některé funkce pro ladění nebo může dojít k poklesu výkonu. Další informace najdete v tématu [ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md).  
  
 Obecně, pokud je hostitelský proces zakázán, platí:  
  
-   Čas potřebný ke spuštění ladění aplikací [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] se zvýší.  
  
-   Vyhodnocení výrazu v době návrhu není k dispozici.  
  
-   Ladění v částečném vztahu důvěryhodnosti není k dispozici.  
  
## <a name="see-also"></a>Viz také

[Ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md)   
[Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)