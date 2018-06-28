---
title: Ladění pomocí prefetched obsah v aplikacích pro UPW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 458b320b971cbb3c4db74d6f2202455332ca5465
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056319"
---
# <a name="debug-uwp-apps-using-prefetched-content-in-visual-studio"></a>Ladění aplikace UWP použitím prefetched obsahu v sadě Visual Studio
  
 Aplikace UWP dosáhnete rychlejší reakce, můžete požádat o Windows přednačtení některé webový obsah, jako jsou webové stránky nebo bitové kopie, do aplikace [WinINet](/windows/desktop/WinInet/about-wininet) mezipaměti. Tato funkce je volána prefetching. Je zvláště efektivní pro obsah, který se používá při spuštění, ale předběžné jiných často používaných obsahu, může načtení příliš. Metody [Windows.Networking.BackgroundTransfer.ContentPrefetcher](/uwp/api/Windows.Networking.BackgroundTransfer.ContentPrefetcher) třída umožňují zadat identifikátory URI, kterou chcete přednačtení obsahu. Sada Windows SDK [předběžné načtení obsahu ukázka](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309) příklady, jak přidat funkce ContentPrefetcher do vaší aplikace.  
  
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