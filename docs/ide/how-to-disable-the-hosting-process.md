---
title: 'Postupy: zákaz procesu hostování'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: f7970ff97c7aec42f8798da07cf2a4a2b6c8bea8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31942058"
---
# <a name="how-to-disable-the-hosting-process"></a>Postupy: zákaz procesu hostování

Je-li povolen hostitelský proces, mohou být volání určitých rozhraní API ovlivněna. V těchto případech je pro vrácení správných výsledků nutné hostitelský proces zakázat.

## <a name="to-disable-the-hosting-process"></a>Zakázání hostitelského procesu

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

- [Ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md)
- [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)