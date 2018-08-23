---
title: 'Postupy: zákaz procesu hostování | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2a3c2eee43d333ee7b58907a8471f4be9815bd47
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631399"
---
# <a name="how-to-disable-the-hosting-process"></a>Postupy: Zákaz procesu hostování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: zákaz procesu hostování](https://docs.microsoft.com/visualstudio/ide/how-to-disable-the-hosting-process).  
  
Je-li povolen hostitelský proces, mohou být volání určitých rozhraní API ovlivněna. V těchto případech je pro vrácení správných výsledků nutné hostitelský proces zakázat.  
  
### <a name="to-disable-the-hosting-process"></a>Zakázání hostitelského procesu  
  
1.  Otevřete projekt spustitelné aplikace v aplikaci [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Projekty, které nevytváří spustitelné soubory (například knihovny tříd nebo projekty služeb) tuto možnost nemají.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
3.  Klikněte na tlačítko **ladění** kartu.  
  
4.  Zrušte **povolit hostující proces sady Visual Studio** zaškrtávací políčko.  
  
 Je-li hostitelský proces zakázán, nebudou k dispozici některé funkce pro ladění nebo může dojít k poklesu výkonu. Další informace najdete v tématu [ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md).  
  
 Obecně, pokud je hostitelský proces zakázán, platí:  
  
-   Čas potřebný ke spuštění ladění aplikací [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] se zvýší.  
  
-   Vyhodnocení výrazu v době návrhu není k dispozici.  
  
-   Ladění v částečném vztahu důvěryhodnosti není k dispozici.  
  
## <a name="see-also"></a>Viz také  
 [Ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md)   
 [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Sestavení během vývoje aplikace](http://msdn.microsoft.com/en-us/c9497d62-3b7b-4449-88e8-cf27acc9efe6)



