---
title: "Postupy: profilování kódu JavaScript na webových stránkách | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript performance profiling
- Profiling Tools,JavaScript
- web site performance profiling
ms.assetid: 37d02aad-ca4d-4eb0-bf66-ca3ecef31fbe
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 61955ead7996a395745a8869bc38c10dc59b537a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>Postupy: profilování kódu JavaScript ve webové stránky
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Nástroje pro profilaci může shromažďovat údaje o výkonu pro kód JavaScript, který se spustí v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, libovolné webové stránky nebo aplikace JavaScript pomocí metoda profilování instrumentace.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
-   Internet Explorer 8 nebo novější.  
  
> [!WARNING]
>  Profil JavaScript v aplikacích pro UPW, najdete v tématu [paměť jazyka JavaScript](../profiling/javascript-memory.md) 
  
 Profilace Průvodce vám pomůže vytvořit relaci výkonu. Zadejte metody instrumentace a pak zadejte JavaScript profilace možnost na stránce instrumentace dialogové okno Vlastnosti výkonnostní relace.  
  
 Když zadáte JavaScript – profilace, kód jazyka JavaScript, která se spouští v prohlížeči a [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] jsou profilovaným kód, který spouští na serveru.  
  
-   Pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, i kód JavaScript, který spouští v prohlížeči a [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] jsou profilovaným kód, který spouští na serveru.  
  
-   Pro webovou stránku libovolný je profilovaným kód JavaScript, který se spustí v prohlížeči.  
  
### <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>Do profilu JavaScript v projektu aplikace ASP.NET  
  
1.  V [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], otevřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webového projektu.  
  
2.  Na **analyzovat** nabídky, klikněte na tlačítko **spusťte Průvodce výkonu**.  
  
3.  Na první stránce průvodce výkonu, zadejte **instrumentace** metoda profilování a pak klikněte na **Další**.  
  
4.  Na druhé stránce průvodce, ujistěte se, zda je aktuální projekt vybrán v seznamu cílů a pak klikněte na tlačítko **Další.**  
  
5.  Na třetí stránce průvodce vyberte **profil JavaScript** zaškrtněte políčko a potom klikněte na **Další**.  
  
6.  Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit** spuštění webové aplikace v prohlížeči.  
  
7.  Výkonu funkce, které chcete profil.  
  
8.  K ukončení relace profilování, zavřete prohlížeč.  
  
### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>Do profilu JavaScript v jednotlivých webové stránky nebo aplikace JavaScript  
  
1.  Otevřete [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)].  
  
2.  Na **analyzovat** nabídky, klikněte na tlačítko **spusťte Průvodce výkonu**.  
  
3.  Na první stránce průvodce výkonu, zadejte **instrumentace** metoda profilování a pak klikněte na **Další**.  
  
4.  Na druhé stránce průvodce, klikněte na aplikace ASP.NET nebo JavaScript a pak klikněte na tlačítko **Další.**  
  
5.  Na třetí stránce průvodce:  
  
    1.  Zadejte adresu URL stránky v **jaké adresu URL nebo cestu aplikaci spustit** pole.  
  
    2.  Vyberte **profil JavaScript** zaškrtněte políčko a potom klikněte na **Další**.  
  
6.  Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit** spustit webovou stránku v prohlížeči.  
  
7.  Výkonu funkce, které chcete profil.  
  
8.  K ukončení relace profilování, zavřete prohlížeč.