---
title: Předběžné načtení obsahu pro aplikace Windows Store | Dokumentace Microsoftu
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
ms.assetid: b4481fef-3ebf-4f7d-9748-d43821a0ebac
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc1b01e0cd841c6239a7f2ef76f964482348ee16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666372"
---
# <a name="prefetch-content-for-windows-store-apps"></a>Předběžné načtení obsahu pro aplikace pro Windows Store
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [předběžné načtení obsahu pro aplikace Windows Store](https://docs.microsoft.com/visualstudio/debugger/prefetch-content-for-windows-store-apps).  
  
Platí pouze pro Windows] (.. /Image/windows_only_content.png "windows_only_content")  
  
 Chcete-li více přizpůsobovat aplikace pro Windows Store, můžete požádat o přednačtení některé webového obsahu, jako je například Image, nebo webové stránky do aplikace Windows [WinINet](http://msdn.microsoft.com/en-us/0a06f2af-957a-4dff-a8cc-187370181b5c)[WinINet](http://msdn.microsoft.com/library/aa383630.aspx)mezipaměti. Tato funkce je volána předběžné načítání. To je zvláště efektivní pro obsah, který se používá při spuštění, ale předběžné další často používané obsah může načtení příliš. Metody [Windows.Networking.BackgroundTransfer.ContentPrefetcher](http://msdn.microsoft.com/library/windows/apps/windows.networking.backgroundtransfer.contentprefetcher.aspx) umožňují zadat identifikátory URI, který chcete předběžné načtení obsahu. Sada Windows SDK [předběžné načtení obsahu ukázka](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309) příklady toho, jak přidat ContentPrefetcher funkce do vaší aplikace.  
  
 Windows používá heuristiky určit, kdy a pokud se předběžné načítání by mělo dojít k a které prostředky se stáhne. Heuristické metody brát v síti účet systému a podmínky napájení, historie využití aplikace uživatele a výsledky předběžného načtení předchozí pokusy. V sadě Visual Studio, můžete použít **předběžné načítání aplikací pro aktivační událost Windows Store** příkaz přinutit Windows ignorovat ContentPrefetcher heuristik a předběžné načtení veškerý obsah, zadaný web. To může být užitečné, pokud chcete otestovat výkon s obsahem pro předběžné načtení do známého stavu (načtení nebo není načtený) nebo chování aplikace.  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>Chcete-li vynutit předběžné načtení z ContentPrefetcher zadané prostředky  
 Tento postup předpokládá, že jste už nastavení funkce ContentPrefetcher a zadat identifikátory URI obsahu přednačtení v projektu aplikace. Chcete-li vynutit předběžné načtení obsahu, pokud zadané prostředky jsou nové nebo upravené, budete muset spuštění a zastavení aplikace, než se rozhodnete **předběžné načítání aplikací pro aktivační událost Windows Store** příkazu. Je-li spustit aplikaci nejprve zaregistrovat identifikátory URI. **Aktivovat předběžné načítání aplikací pro Windows Store** příkaz pak vynutí ContentPrefetcher ke stažení obsahu a přidat ho do mezipaměti. Při dalším spuštění aplikace můžete předpokládat, že obsah se předem načtou.  
  
1.  Spustí aplikaci pro registraci předběžné načtení obsahu identifikátory URI v aplikaci. Na **ladění** nabídce zvolte **spustit ladění** (Klávesová zkratka: F5).  
  
2.  Na **ladění** nabídce zvolte **Zastavit ladění** (Klávesová zkratka: Shift + F5).  
  
3.  Na **ladění** nabídce zvolte **jiné cíle ladění** a klikněte na tlačítko **předběžné načítání aplikací pro aktivační událost Windows Store**.  
  
 Teď můžete ladit, testování nebo analyzovat aplikace s využitím předem načteného webových prostředků.  
  
> [!NOTE]
>  Tento postup opakujte, pokaždé, když přidáváte nebo odebíráte Zadaný webový obsah.  
  
## <a name="see-also"></a>Viz také  
 [Blogový příspěvek: Aktivace předběžné načtení pro Windows Store aplikace ve Visual Studio 2013 Update 2](http://blogs.msdn.com/b/visualstudioalm/archive/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2.aspx)



