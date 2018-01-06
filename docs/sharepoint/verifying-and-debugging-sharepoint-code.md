---
title: "Zobrazení a ladění kódu služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- unit testing [SharePoint development in Visual Studio]
- IntelliTrace [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, IntelliTrace
- SharePoint development in Visual Studio, unit testing
ms.assetid: b5f3bce2-6a51-41b1-a292-9e384bae420c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d3717d3bee3665705ce39307b640e02a931cd75f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="verifying-and-debugging-sharepoint-code"></a>Zobrazení a ladění kódu pro SharePoint
  Pomocí IntelliTrace a testování částí lze snadněji ladit řešení služby SharePoint a zajistit správnou funkčnost každé metody. Tyto funkce lze v aplikaci [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] použít pro projekty služby SharePoint podle stejných postupů, které jsou platné pro ostatní typy v projektu.  
  
## <a name="intellitrace"></a>IntelliTrace  
 Pomocí IntelliTrace lze určit nejen aktuální stav řešení služby SharePoint, ale také událostí, ke kterým došlo v minulosti, a kontext, ve kterém k nim došlo. V řešení služby SharePoint lze přecházet zpět a vpřed do různých bodů, kdy byly zaznamenány události, a prohlížet stav a hodnoty proměnných v každém tomto bodě. Pomocí této dynamické navigace lze snadno a rychle ladit řešení služby SharePoint bez nutnosti nastavení mnoha zarážek. Je také možné uložit relaci ladění do souboru protokolu IntelliTrace (.iTrace), otevřít jej později v aplikaci Visual Studio Ultimate a ladění po poruše. Soubor .iTrace obsahuje podrobné informace o konkrétní chyby služby SharePoint se stalo, kdy a kde, tak, aby můžete snadněji zjistit příčinu chyby. Informace v souboru .iTrace je podmnožina úplného protokolu chyb, který je vytvořen v rámci služby SharePoint v systému Unified Logging System (ULS). Tyto informace zahrnují události, které jsou specifické pro službu SharePoint, například kdy byl otevřen nebo zavřen profil uživatele a kdy byly načteny, přečteny nebo změněny vlastnosti projektu služby SharePoint. Je možné nastavit, které události IntelliTrace zaznamená. Další informace najdete v tématu [pomocí uložit dat technologie IntelliTrace](/visualstudio/debugger/using-saved-intellitrace-data) a [konfigurace IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
 Dojde-li ve službě SharePoint k chybám, zobrazí dialogové okno identifikátor „ID korelace“ konkrétní chyby. ID korelace lze také získat z událostí, které jsou uvedeny v souboru .iTrace. Pokud chcete zobrazit seznam všech událostí, které se stalo s danou korelační ID, můžete zadat ID v **Analysis** části souhrnná stránka IntelliTrace. V této části můžete zadat, zda chcete zobrazit pouze názvy událostí, ke kterým došlo, nebo názvy událostí a informace o jejich volání, dále název funkce, vstupní a výstupní body, parametry a návratové hodnoty.  
  
 Události v sadě Visual Studio můžete získat v IntelliTrace výběrem **F5** klíč. Chcete-li získat události, které jsou specifické pro službu SharePoint, musíte shromáždit data IntelliTrace v rámci řešení služby SharePoint pomocí nástroje Microsoft Monitoring Agent. Tento nástroj shromažďuje data IntelliTrace a vytváří soubory .iTrace pro aplikace, které jsou nasazeny mimo aplikaci Visual Studio. Další informace najdete v tématu [funkce IntelliTrace](/visualstudio/debugger/intellitrace-features) a [pomocí samostatného kolektoru IntelliTrace](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).  
  
## <a name="unit-testing"></a>Testování částí  
 Chyby lze v kódu snadněji vyhledat pomocí testování částí, ve kterých je kód psán a spouštěn v rámci testovacích metod. Tyto metody obsahují prázdné proměnné a kontrolní příkaz, který slouží k ověření logiky a funkčnosti projektu založeného na modelu objektu služby SharePoint. Další informace najdete v tématu [si kód Test jednotky](/visualstudio/test/unit-test-your-code).  
  
### <a name="support-for-microsoft-fakes-framework"></a>Podpora rozhraní Microsoft Fakes  
 Projekty služby SharePoint podporují Microsoft Fakes, což je izolované rozhraní, ve kterém lze vytvářet zkušební kódy na základě delegátů a překryvných ovladačů v aplikacích, které jsou založeny na rozhraní .NET Framework. Pomocí rozhraní Fakes lze vytvářet, spravovat a zakládat fiktivní implementace v rámci testování součástí. Tyto kódy a překryvné ovladače izolují testování částí od prostředí. Zkušební kód lze vytvářet pro testování kódu, který spotřebovává rozhraní nebo nezapečetěné třídy skrze přepisovatelné metody. Překryvné ovladače lze vytvořit pro přesměrování zapečetěných tříd se statickými metodami nebo metodami, které nelze přepsat do alternativní překryvné implementace. Zkušební kód a překryvné ovladače lze také použít pro dynamické nastavení chování jednotlivých zkušebních členů. Další informace najdete v tématu [izolace kódu v rámci testu s Microsoft Fakes](/visualstudio/test/isolating-code-under-test-with-microsoft-fakes).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[IntelliTrace](/visualstudio/debugger/intellitrace)|Tento článek popisuje snadnější ladění řešení aplikace Visual Studio pomocí IntelliTrace.|  
|[Návod: Ladění aplikace SharePoint s použitím technologie IntelliTrace](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)|Znázorňuje způsob vyhledávání chyb při programování v projektu služby SharePoint pomocí IntelliTrace.|  
|[Testování částí kódu](/visualstudio/test/unit-test-your-code)|Popisuje, jak najít logické chyby v kódu pomocí testování částí.|  
  
## <a name="see-also"></a>Viz také  
 [Zlepšení kvality kódu](/visualstudio/test/improve-code-quality)  
  
  