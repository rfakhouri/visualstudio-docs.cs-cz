---
title: Ladění a proces hostování | Microsoft Docs
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
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04d6500ba45b10a4cc6a309e7f60872febc19736
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481512"
---
# <a name="debugging-and-the-hosting-process"></a>Ladění a proces hostování
Proces hostování sady Visual Studio zlepšuje ladicího programu a umožňuje nové funkce ladicího programu, jako je ladění částečným vztahem důvěryhodnosti a vyhodnocení výrazu při návrhu. Pokud potřebujete, můžete zákaz procesu hostování. Další informace najdete v tématu [postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md). Následující části popisují některé rozdíly mezi ladění a bez hostitelského procesu.  
  
## <a name="partial-trust-debugging-and-click-once-security"></a>Ladění částečným vztahem důvěryhodnosti a klikněte na tlačítko-jednou zabezpečení  
 Proces hostování ladění částečným vztahem důvěryhodnosti vyžaduje. Pokud zakážete hostitelského procesu, ladění částečným vztahem důvěryhodnosti nebude fungovat i v případě, že částečným vztahem důvěryhodnosti je zabezpečená **zabezpečení** stránka **vlastnosti projektu**. Další informace najdete v tématu [postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md) a [postupy: ladění aplikace částečné důvěryhodnosti](../debugger/how-to-debug-a-partial-trust-application.md).  
  
## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu při návrhu  
 Vždy výrazu při návrhu používá proces hostování. Zakázání, který je hostitelem zpracovat **vlastnosti projektu** zakáže vyhodnocení výrazu při návrhu u projektů knihovny tříd. Pro jiné typy projektů není zakázáno vyhodnocení výrazu při návrhu. Místo toho Visual Studio spustí skutečné spustitelný soubor a používá je pro zkušební doby návrhu bez hostitelského procesu. Tento rozdíl může mít různé výsledky.  
  
## <a name="appdomaincurrentdomainfriendlyname-differences"></a>Rozdíly AppDomain.CurrentDomain.FriendlyName  
 `AppDomain.CurrentDomain.FriendlyName` Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelského procesu. Když zavoláte `AppDomain.CurrentDomain.FriendlyName` s hostitelského procesu povolené, vrátí *app_name*`.vhost.exe`. Pokud provádíte volání je proces hostování zakázáno, vrátí *app_name*`.exe`.  
  
## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). Rozdíly FullName  
 `Assembly.GetCallingAssembly().FullName` Vrátí odlišné výsledky v závislosti na tom, zda je povoleno hostitelského procesu. Když zavoláte `Assembly.GetCallingAssembly().FullName` s hostitelského procesu povolené, vrátí `mscorlib`. Když zavoláte `Assembly.GetCallingAssembly().FullName` s hostitelského procesu zakázáno, vrátí název aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Postupy: ladění aplikace s částečnou důvěryhodností](../debugger/how-to-debug-a-partial-trust-application.md)   
 [Postupy: Zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md)