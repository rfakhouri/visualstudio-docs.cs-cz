---
title: Ladění a proces hostování | Dokumentace Microsoftu
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
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 10f3968367b188203671fa6bfff48bc482efe4f7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157900"
---
# <a name="debugging-and-the-hosting-process"></a>Ladění a proces hostování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Hostující proces sady Visual Studio zlepšuje výkon ladicího programu a umožňuje nové funkce ladicího programu, jako je ladění částečným vztahem důvěryhodnosti a vyhodnocení výrazu v době návrhu. Pokud je potřeba, můžete zákaz procesu hostování. Další informace najdete v tématu [jak: Zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md). Následující části popisují některé rozdíly mezi ladění a nemusíte hostitelský proces.  
  
## <a name="partial-trust-debugging-and-click-once-security"></a>Ladění částečným vztahem důvěryhodnosti a klikněte na tlačítko-jednou zabezpečení  
 Ladění částečným vztahem důvěryhodnosti vyžaduje hostující proces. Pokud je hostitelský proces zakázat, částečným vztahem důvěryhodnosti ladění nebudou fungovat i v případě, že je zapnutá částečným vztahem důvěryhodnosti zabezpečení **zabezpečení** stránce **vlastnosti projektu**. Další informace najdete v tématu [jak: Zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md) a [jak: Ladění aplikace s částečnou důvěryhodností](../debugger/how-to-debug-a-partial-trust-application.md).  
  
## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu v době návrhu  
 Výraz návrhu vždy používá hostitelský proces. Zakázání hostování v procesu **vlastnosti projektu** zakáže vyhodnocení výrazu v době návrhu pro projekty knihovny tříd. Vyhodnocení výrazu v době návrhu není zakázáno, pro ostatní typy projektů. Místo toho Visual Studio spustí skutečný program a použije ho k vyhodnocení doby návrhu bez hostitelský proces. Tento rozdíl může mít různé výsledky.  
  
## <a name="appdomaincurrentdomainfriendlyname-differences"></a>AppDomain.CurrentDomain.FriendlyName Differences  
 `AppDomain.CurrentDomain.FriendlyName` Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelský proces. Při volání `AppDomain.CurrentDomain.FriendlyName` s proces hostování povoleno, vrátí *app_name*`.vhost.exe`. Pokud při volání hostitelský proces zakázán, vrátí *app_name*`.exe`.  
  
## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). Jméno a příjmení rozdíly  
 `Assembly.GetCallingAssembly().FullName` Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelský proces. Při volání `Assembly.GetCallingAssembly().FullName` s proces hostování povoleno, vrátí `mscorlib`. Při volání `Assembly.GetCallingAssembly().FullName` se hostitelský proces zakázán, vrátí název aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Postupy: Ladění aplikace s částečnou důvěryhodností](../debugger/how-to-debug-a-partial-trust-application.md)   
 [Postupy: Zakázání hostitelského procesu](../ide/how-to-disable-the-hosting-process.md)
