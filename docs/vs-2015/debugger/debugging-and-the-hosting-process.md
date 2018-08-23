---
title: Ladění a proces hostování | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5cc008f12f4312df2d63f019a0d33a7b727e5ae
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629949"
---
# <a name="debugging-and-the-hosting-process"></a>Ladění a proces hostování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ladění a proces hostování](https://docs.microsoft.com/visualstudio/debugger/debugging-and-the-hosting-process).  
  
Hostující proces sady Visual Studio zlepšuje výkon ladicího programu a umožňuje nové funkce ladicího programu, jako je ladění částečným vztahem důvěryhodnosti a vyhodnocení výrazu v době návrhu. Pokud je potřeba, můžete zákaz procesu hostování. Další informace najdete v tématu [postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md). Následující části popisují některé rozdíly mezi ladění a nemusíte hostitelský proces.  
  
## <a name="partial-trust-debugging-and-click-once-security"></a>Ladění částečným vztahem důvěryhodnosti a klikněte na tlačítko-jednou zabezpečení  
 Ladění částečným vztahem důvěryhodnosti vyžaduje hostující proces. Pokud je hostitelský proces zakázat, částečným vztahem důvěryhodnosti ladění nebudou fungovat i v případě, že je zapnutá částečným vztahem důvěryhodnosti zabezpečení **zabezpečení** stránce **vlastnosti projektu**. Další informace najdete v tématu [postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md) a [postupy: ladění aplikace částečné důvěryhodnosti](../debugger/how-to-debug-a-partial-trust-application.md).  
  
## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu v době návrhu  
 Výraz návrhu vždy používá hostitelský proces. Zakázání hostování v procesu **vlastnosti projektu** zakáže vyhodnocení výrazu v době návrhu pro projekty knihovny tříd. Vyhodnocení výrazu v době návrhu není zakázáno, pro ostatní typy projektů. Místo toho Visual Studio spustí skutečný program a použije ho k vyhodnocení doby návrhu bez hostitelský proces. Tento rozdíl může mít různé výsledky.  
  
## <a name="appdomaincurrentdomainfriendlyname-differences"></a>AppDomain.CurrentDomain.FriendlyName rozdíly  
 `AppDomain.CurrentDomain.FriendlyName` Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelský proces. Při volání `AppDomain.CurrentDomain.FriendlyName` s proces hostování povoleno, vrátí *app_name*`.vhost.exe`. Pokud při volání hostitelský proces zakázán, vrátí *app_name*`.exe`.  
  
## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). Jméno a příjmení rozdíly  
 `Assembly.GetCallingAssembly().FullName` Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelský proces. Při volání `Assembly.GetCallingAssembly().FullName` s proces hostování povoleno, vrátí `mscorlib`. Při volání `Assembly.GetCallingAssembly().FullName` se hostitelský proces zakázán, vrátí název aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Postupy: ladění aplikace s částečnou důvěryhodností](../debugger/how-to-debug-a-partial-trust-application.md)   
 [Postupy: Zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md)



