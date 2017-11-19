---
title: "Ladění pomocí prefetched obsah v aplikacích pro UPW | Microsoft Docs"
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
ms.assetid: b4481fef-3ebf-4f7d-9748-d43821a0ebac
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d85c76ce48ca2e04e7ce40b9e40075c8ba539e6
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="debug-uwp-apps-using-prefetched-content-in-visual-studio"></a>Ladění aplikace UWP použitím prefetched obsahu v sadě Visual Studio
![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Aplikace UWP dosáhnete rychlejší reakce, můžete požádat o Windows přednačtení některé webový obsah, jako jsou webové stránky nebo bitové kopie, do aplikace [WinINet](http://msdn.microsoft.com/en-us/0a06f2af-957a-4dff-a8cc-187370181b5c)[WinINet](http://msdn.microsoft.com/library/aa383630.aspx)mezipaměti. Tato funkce je volána prefetching. Je zvláště efektivní pro obsah, který se používá při spuštění, ale předběžné jiných často používaných obsahu, může načtení příliš. Metody [Windows.Networking.BackgroundTransfer.ContentPrefetcher](http://msdn.microsoft.com/library/windows/apps/windows.networking.backgroundtransfer.contentprefetcher.aspx) třída umožňují zadat identifikátory URI, kterou chcete přednačtení obsahu. Sada Windows SDK [předběžné načtení obsahu ukázka](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309) příklady, jak přidat funkce ContentPrefetcher do vaší aplikace.  
  
 Systém Windows použije heuristiku k určení Pokud a v případě prefetching provedeno a prostředky, ke kterým se budou stahovat. Heuristiky brát v síti systému účet a podmínky napájení, historie využití aplikace uživatele a výsledky pokusů o předběžné načtení předchozí. V sadě Visual Studio, můžete použít **předběžného načtení aplikace aktivační události systému Windows Store** příkaz vynutit ignorovat ContentPrefetcher heuristiky a přednačtení všechny zadané webového obsahu. To může být užitečné, pokud chcete otestovat výkon s obsahem pro předběžné načtení ve známého stavu (načtena nebo není načtená.) nebo chování aplikace.  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>Chcete-li vynutit předběžného načítání systému ContentPrefetcher zadané prostředky  
 Tento postup předpokládá, že jste již nastavit funkci ContentPrefetcher a zadat obsahu identifikátory URI přednačtení v projektu aplikace. Chcete-li vynutit předběžného načítání obsahu, pokud zadané prostředky jsou nové nebo upravené, budete muset spustit a zastavit aplikaci, než vyberete **předběžného načtení aplikace aktivační události systému Windows Store** příkaz. Je-li spustit aplikaci nejprve zaregistrovat identifikátory URI. **Spustit předběžné načtení ve Windows Store aplikace** příkaz pak vynutí ContentPrefetcher stažení obsahu a přidat ho do mezipaměti. V při dalším spuštění aplikace můžete předpokládat, že se předem načtou obsah.  
  
1.  Spusťte aplikaci zaregistrovat předběžné načtení obsahu identifikátory URI v aplikaci. Na **ladění** nabídce zvolte **spustit ladění** (klávesové zkratky: F5).  
  
2.  Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové zkratky: Shift + F5).  
  
3.  Na **ladění** nabídce zvolte **jiné cíle ladění** a potom zvolte **předběžného načtení aplikace aktivační události systému Windows Store**.  
  
 Nyní můžete ladění, testování nebo analyzovat vaší aplikace pomocí prefetched webové prostředky.  
  
> [!NOTE]
>  Opakujte tyto kroky vždy, když přidáváte nebo odebíráte zadaný webového obsahu.  
  
## <a name="see-also"></a>Viz také  
 [Příspěvek blogu: spouštění předběžné načtení pro aplikace Windows Store v sadě Visual Studio 2013 Update 2](http://blogs.msdn.com/b/visualstudioalm/archive/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2.aspx)