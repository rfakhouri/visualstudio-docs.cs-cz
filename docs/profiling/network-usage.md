---
title: Analýza využití sítě v aplikacích pro UPW v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 45fa397d-d7a1-4c4c-9c97-ede6c21643bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5221b8683a871baec94bea144d22932832cad77e
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256081"
---
# <a name="analyze-network-usage-in-uwp-apps"></a>Analýza využití sítě v aplikacích pro UPW
Visual Studio **sítě** nástroj diagnostiky shromažďuje informace o síťových operací provést pomocí [Windows.Web.Http API](/uwp/api/windows.web.http). Analyzuje data vám může pomoct vyřešit problémy, jako je přístup a ověřování problémy, nesprávné použití mezipaměti a nízký zobrazení a stažení výkonu.  
  
 Nástroj sítě podporuje pouze aplikace UWP. V tuto chvíli nepodporuje jiné platformy.  
  
> [!NOTE]
>  Podrobnější popis nástroje sítě najdete v tématu [nástroj síťových představení sady Visual Studio](http://blogs.msdn.com/b/visualstudio/archive/2015/05/04/introducing-visual-studios-network-tool.aspx).  
  
## <a name="collect-network-tool-data"></a>Shromažďovat data nástroj sítě.  
 Byste měli spustit **sítě** nástroj s projektu sady Visual Studio otevřete v sadě Visual Studio počítači.  
  
1.  Otevřete projekt v sadě Visual Studio.  
  
2.  V nabídce klikněte na tlačítko **ladění nebo výkonu profileru**. Zvolte **sítě**a potom zvolte **spustit**.  
  
3.  Nástroj sítě začne shromažďovat informace o přenosech HTTP vaší aplikace.  
  
     Souhrnné zobrazení v levém podokně spustíte aplikaci, automaticky zobrazuje seznam zaznamenané operací protokolu HTTP. Vyberte položku na souhrnné zobrazení zobrazíte další informace v panelu podrobností v pravém podokně.  
  
4.  Zvolte **Zastavit** aplikace se zavře.  
  
 Okno sestavy by měla vypadat přibližně takto:  
  
 ![Okno sítě](../profiling/media/network_fullwindow.png "NETWORK_FullWindow")  
  
## <a name="analyze-data"></a>Analýza dat  
 Zachycená data protokolu HTTP můžete analyzovat, když aplikace běží, nebo i po zavření aplikace, vyberte některým ze sítě zobrazit na souhrnné zobrazení.  
  
 **Sítě** souhrnné zobrazení zobrazuje data pro každou operaci sítě při spuštění aplikace. Zvolte záhlaví sloupce seřadíte seznam, nebo zvolte typy obsahu k zobrazení v **typ obsahu** filtrovat zobrazení.  
  
 Vyberte **uložit jako HAR** vytvořte soubor JSON, který mohou být spotřebovávána nástroje třetích stran, například aplikaci Fiddler.  
  
 **Sítě** zobrazení podrobností se zobrazí další informace o síťové operace v souhrnné zobrazení.  
  
 ![Podokno podrobností nástroj sítě](../profiling/media/network_detailsviewpane.png "NETWORK_DetailsViewPane")  
  
|||  
|-|-|  
|**Záhlaví**|Informace o hlavičkách žádostí události.|  
|**Text**|Data datová část požadavku a odpovědi.|  
|**Parametry**|Názvy parametrů řetězce dotazu a hodnoty.|  
|**Soubory cookie**|Data cookie odpovědi a požadavku.|  
|**Časování**|Graf fázích při získávání vybrané prostředky.|  
  
 Síť **souhrnné** panel zobrazuje počet síťových operací, které se zobrazují v libovolném časovém okamžiku, kolik dat se přenesl, jak dlouho trvalo a stahovat je a kolik chyby (požadavků s odpovědí 4xx nebo 5xx) jsou viditelné.  
  
### <a name="analysis-tips"></a>Tipy pro analýzu  
 Tento nástroj upozorňuje určité oblasti, které mohou být užitečné, pokud používáte analysis související se sítí:  
  
1.  Požadavky, které jsou plně obsluhovat z mezipaměti se zobrazují jako **(z mezipaměti)** v **přijaté** sloupce. Můžete určit, jestli používáte mezipaměti efektivně uložit uživatelskou šířku pásma, nebo zda omylem ukládání odpovědí do mezipaměti a poskytuje koncového uživatele vaší aplikace pomocí zastaralá data.  
  
2.  Chybové odpovědi (4xx nebo 5xx) se zobrazí v **výsledky** sloupec červený stav kódu a taky jsou vyznačené na panelu souhrnu. Díky tomu je snadné sledovat chyby mezi mnoho potenciální požadavků ve vaší aplikaci.  
  
3.  Tlačítko odpovědi poměrně tisk (uvnitř kartě textu) můžete analyzovat prostřednictvím formátu JSON, XML, HTML, CSS, JavaScript a TypeScript datové části odpovědi zvýšením čitelnost obsahu.  
  
## <a name="see-also"></a>Viz také:  
 [Spouštění nástrojů pro profilaci s ladicím programem nebo bez něj](../profiling/running-profiling-tools-with-or-without-the-debugger.md)  
 [Visual Studio blog: inspector sítě představení sady Visual Studio](http://go.microsoft.com/fwlink/?LinkId=535022)   
 [Video Channel 9: VS diagnostické nástroje – nové sítě profileru](http://channel9.msdn.com/Series/ConnectOn-Demand/206)  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md)
