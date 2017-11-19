---
title: "Co je nového v ladicím programu Visual Studio 2017 | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2016
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
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
caps.latest.revision: "81"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a08c56ae60822e6d4183e5789c68cbe383b4dd5
ms.sourcegitcommit: 2c7f48ad6073a81fa927568793633f26cc1f0b15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/17/2017
---
# <a name="whats-new-for-the-debugger-in-includevsdev15miscincludesvsdev15mdmd"></a>Co je nového v ladicím programu[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Ladicí program obsahuje tyto nové funkce:

- Nové v 15,5, **ladicí program snímku** pořídí snímek aplikací v provozním když provede kód, který vás zajímá. Dáte pokyn, aby ladicí program na pořízení snímku, nastavte snappoints a logpoints ve vašem kódu. Ladicí program umožňuje zobrazit přesně kde došlo k chybě, bez vlivu na provoz produkční aplikace. Ladicí program snímku můžete výrazně zkrátit dobu potřebnou k vyřešení problémů, ke kterým došlo v produkčním prostředí.

    Snímek kolekce je k dispozici pro následující webové aplikace běžící v Azure App Service:

    * Aplikace ASP.NET spuštěné na rozhraní .NET Framework 4.6.1 nebo novější.
    * ASP.NET Core aplikací běžících na .NET Core 2.0 nebo novější na systému Windows.

    Další informace najdete v tématu [ladění za provozu aplikace ASP.NET pomocí ladicího programu snímku](../debugger/debug-live-azure-applications.md).

- Nové v 15,5 ve Visual Studio Enterprise pouze **zpětný krok IntelliTrace** automaticky vytvoří snímek vaší aplikace v každé zarážek a ladicí program krok události. Zaznamenaná snímky umožňují přejděte zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti. IntelliTrace zpětný krok vám může ušetřit čas když chcete zobrazit předchozí stav aplikace, ale nechcete, aby se znovu spustit ladění nebo znovu vytvořte stav požadované aplikace.

    Můžete vyhledat a zobrazit snímky pomocí **krok zpětné** a **krok dál** tlačítek na panelu nástrojů ladění. Tato tlačítka přejděte události, které se zobrazují v **události** ve **diagnostické nástroje** okno.

    ![Krok tlačítka vpřed a zpět](../debugger/media/intellitrace-step-back-icons-description.png  "krok zpět a jejich předávání tlačítka")

    Další informace najdete v tématu [zobrazit snímky IntelliTrace zpětným krok pomocí](../debugger/how-to-use-intellitrace-step-back.md) stránky.

- **Pomocníka výjimka** nahrazuje Pomocníka pro výjimky a se zobrazí v nemodálním dialogovém kde došlo k chybě. **Pomocníka výjimka** poskytuje rychlejší přístup k žádné vnitřní výjimky, další analýzu, ladicího programu (Pokud je k dispozici) a okamžitý přístup k **nastavení výjimky** pro výjimku. Pomocníka výjimka můžete také přetáhnout plovoucí zobrazení, pokud blokuje něco, co potřebujete zobrazit.

    Například **NullReferenceException** nyní zobrazuje proměnné, která obsahuje odkaz na hodnotu null (Další informace o).

    ![Ladicí program na pomocníka výjimka](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    Další informace najdete v tématu [pomocí nového pomocníka výjimka v sadě Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/) příspěvku na blogu.

- Teď můžete spustit na řádek kódu při pozastavena v ladicím programu výběrem **spuštění zde** ikonu zelenou šipku (při se zobrazí ikona ukazatele myši na řádek kódu). Tím se eliminuje potřeba nastavit dočasné zarážky.

    ![Ladicí program je spustit kliknutím](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

- Podmínky můžete nastavit výjimky v **nastavení výjimky** dialogové okno (můžete to provést pomocí **upravit podmínky** v dialogovém okně Nastavení výjimky nebo pomocí v místní nabídce na ikonu došlo k výjimce.) Aktuálně podporované podmínky zahrnují názvy modulu pro zahrnutí nebo vyloučení pro výjimku.

    ![Podmínky se u výjimku](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- Připojte k procesu dialogové okno obsahuje novou funkci vyhledávání, která vám může pomoct další rychle identifikovat proces, který je potřeba přiřadit.

    ![Hledání v připojit k procesu](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch") 

Další informace o těchto nových funkcích najdete v tématu [poznámky k verzi pro [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag).
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)