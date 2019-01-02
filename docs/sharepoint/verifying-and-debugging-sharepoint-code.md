---
title: Zobrazení a ladění kódu pro SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- unit testing [SharePoint development in Visual Studio]
- IntelliTrace [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, IntelliTrace
- SharePoint development in Visual Studio, unit testing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1705e77472ba9b8fa7a01d047c0aadaf342b7932
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916832"
---
# <a name="verify-and-debug-sharepoint-code"></a>Ověřte a ladění kódu pro SharePoint
Pomocí IntelliTrace a testování částí lze snadněji ladit řešení služby SharePoint a zajistit správnou funkčnost každé metody. Tyto funkce můžete použít pro projekty služby SharePoint v sadě Visual Studio podle stejného postupu jako u ostatních typů projektů.

## <a name="intellitrace"></a>Intellitrace
Pomocí IntelliTrace lze určit nejen aktuální stav řešení služby SharePoint, ale také událostí, ke kterým došlo v minulosti, a kontext, ve kterém k nim došlo. V řešení služby SharePoint lze přecházet zpět a vpřed do různých bodů, kdy byly zaznamenány události, a prohlížet stav a hodnoty proměnných v každém tomto bodě. Pomocí této dynamické navigace lze snadno a rychle ladit řešení služby SharePoint bez nutnosti nastavení mnoha zarážek. Můžete také uložit relaci ladění do protokolu IntelliTrace (*.iTrace*) soubor, otevřete ho později v sadě Visual Studio Enterprise a ladění po poruše. *.ITrace* soubor obsahuje podrobné informace o kdy a kde došlo k určitým chybám služby SharePoint, takže můžete snadno zjistit, co je příčinou chyby. Informace v *.iTrace* je podmnožina úplného protokolu chyb, který sjednoceného systému protokolování (ULS) v Sharepointu vytvoří soubor. Tyto informace zahrnují události, které jsou specifické pro službu SharePoint, například kdy byl otevřen nebo zavřen profil uživatele a kdy byly načteny, přečteny nebo změněny vlastnosti projektu služby SharePoint. Je možné nastavit, které události IntelliTrace zaznamená. Další informace najdete v tématu [použití uložených dat řešení IntelliTrace](../debugger/using-saved-intellitrace-data.md).

Dojde-li ve službě SharePoint k chybám, zobrazí dialogové okno identifikátor „ID korelace“ konkrétní chyby. ID korelace lze také získat z událostí, které jsou uvedeny v *.iTrace* souboru. Chcete-li zobrazit seznam všech událostí, ke kterým došlo s daným ID korelace, můžete zadat ID v **analýzy** části na stránce souhrnu IntelliTrace. V této části můžete zadat, zda chcete zobrazit pouze názvy událostí, ke kterým došlo, nebo názvy událostí a informace o jejich volání, dále název funkce, vstupní a výstupní body, parametry a návratové hodnoty.

Události aplikace Visual Studio v IntelliTrace můžete získat kliknutím **F5** klíč. Chcete-li získat události, které jsou specifické pro službu SharePoint, musíte shromáždit data IntelliTrace v rámci řešení služby SharePoint pomocí nástroje Microsoft Monitoring Agent. Tento nástroj shromažďuje IntelliTrace data a vytvoří *.iTrace* souborů pro aplikace, které jsou nasazeny mimo sadu Visual Studio. Další informace najdete v tématu [funkce IntelliTrace](../debugger/intellitrace-features.md) a [použití samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md).

## <a name="unit-test"></a>Testování částí
Chyby lze v kódu snadněji vyhledat pomocí testování částí, ve kterých je kód psán a spouštěn v rámci testovacích metod. Tyto metody obsahují prázdné proměnné a kontrolní příkaz, který slouží k ověření logiky a funkčnosti projektu založeného na modelu objektu služby SharePoint. Další informace najdete v tématu [svůj kód testu jednotek](../test/unit-test-your-code.md).

### <a name="support-for-microsoft-fakes-framework"></a>Podpora rozhraní Microsoft Fakes
Projekty služby SharePoint podporují Microsoft Fakes, což je izolované rozhraní, ve kterém lze vytvářet zkušební kódy na základě delegátů a překryvných ovladačů v aplikacích, které jsou založeny na rozhraní .NET Framework. Pomocí rozhraní Fakes lze vytvářet, spravovat a zakládat fiktivní implementace v rámci testování součástí. Tyto kódy a překryvné ovladače izolují testování částí od prostředí. Zkušební kód lze vytvářet pro testování kódu, který spotřebovává rozhraní nebo nezapečetěné třídy skrze přepisovatelné metody. Překryvné ovladače lze vytvořit pro přesměrování zapečetěných tříd se statickými metodami nebo metodami, které nelze přepsat do alternativní překryvné implementace. Zkušební kód a překryvné ovladače lze také použít pro dynamické nastavení chování jednotlivých zkušebních členů. Další informace najdete v tématu [izolace kódu v rámci testu s Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md).

## <a name="related-articles"></a>Související články

|Název|Popis|
|-----------|-----------------|
|[IntelliTrace](../debugger/intellitrace.md)|Tento článek popisuje snadnější ladění řešení aplikace Visual Studio pomocí IntelliTrace.|
|[Návod: Ladění aplikace SharePoint s použitím technologie IntelliTrace](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)|Znázorňuje způsob vyhledávání chyb při programování v projektu služby SharePoint pomocí IntelliTrace.|
|[Testování částí kódu](../test/unit-test-your-code.md)|Popisuje, jak najít logické chyby v kódu pomocí testování částí.|

## <a name="see-also"></a>Viz také:

- [Zlepšení kvality kódu](../test/improve-code-quality.md)