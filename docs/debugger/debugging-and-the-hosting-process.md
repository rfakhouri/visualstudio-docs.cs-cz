---
title: "Ladění a proces hostování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02cdf8b50415a238c2af2735a20fea4ed8c23668
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-and-the-hosting-process"></a>Ladění a proces hostování
Proces hostování sady Visual Studio zlepšuje ladicího programu a umožňuje nové funkce ladicího programu, jako je ladění částečným vztahem důvěryhodnosti a vyhodnocení výrazu při návrhu. Pokud potřebujete, můžete zákaz procesu hostování. Další informace najdete v tématu [postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md). Následující části popisují některé rozdíly mezi ladění a bez hostitelského procesu.  
  
## <a name="partial-trust-debugging-and-click-once-security"></a>Ladění částečným vztahem důvěryhodnosti a klikněte na tlačítko-jednou zabezpečení  
 Proces hostování ladění částečným vztahem důvěryhodnosti vyžaduje. Pokud zakážete hostitelského procesu, ladění částečným vztahem důvěryhodnosti nebude fungovat i v případě, že částečným vztahem důvěryhodnosti je zabezpečená **zabezpečení** stránka **vlastnosti projektu**. Další informace najdete v tématu [postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md) a [postupy: ladění aplikace částečné důvěryhodnosti](../debugger/how-to-debug-a-partial-trust-application.md).  
  
## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu při návrhu  
 Vždy výrazu při návrhu používá proces hostování. Zakázání, který je hostitelem zpracovat **vlastnosti projektu** zakáže vyhodnocení výrazu při návrhu u projektů knihovny tříd. Pro jiné typy projektů není zakázáno vyhodnocení výrazu při návrhu. Místo toho Visual Studio spustí skutečné spustitelný soubor a používá je pro zkušební doby návrhu bez hostitelského procesu. Tento rozdíl může mít různé výsledky.  
  
## <a name="appdomaincurrentdomainfriendlyname-differences"></a>Rozdíly AppDomain.CurrentDomain.FriendlyName  
 `AppDomain.CurrentDomain.FriendlyName`Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelského procesu. Když zavoláte `AppDomain.CurrentDomain.FriendlyName` s hostitelského procesu povolené, vrátí *app_name*`.vhost.exe`. Pokud provádíte volání je proces hostování zakázáno, vrátí *app_name*`.exe`.  
  
## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). Rozdíly FullName  
 `Assembly.GetCallingAssembly().FullName`Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelského procesu. Když zavoláte `Assembly.GetCallingAssembly().FullName` s hostitelského procesu povolené, vrátí `mscorlib`. Když zavoláte `Assembly.GetCallingAssembly().FullName` s hostitelského procesu zakázáno, vrátí název aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Postupy: ladění aplikace s částečnou důvěryhodností](../debugger/how-to-debug-a-partial-trust-application.md)   
 [Postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md)