---
title: Rozšířené dialogové okno nastavení (vizualizér souběžnosti) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.settings
ms.assetid: bb3d90aa-5f08-4953-9be0-be6cea11633d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 719adce78c2a1a5ec1d9a15eea69769c476c6170
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="advanced-settings-dialog-box-concurrency-visualizer"></a>Dialogové okno Upřesnit nastavení (Vizualizér souběžnosti)
Pomocí **Upřesnit nastavení** dialogové okno vizualizér souběžnosti můžete řídit, jak se shromažďují trasování.  Dialogové okno obsahuje karty pro symboly, pouze můj kód, ukládání do vyrovnávací paměti, filtrování, CLR události, značek, zprostředkovatele a soubory.  
  
## <a name="symbols"></a>Symboly  
 Vizualizér souběžnosti používá stejné nastavení symbol jako Visual Studio Debugger. Vizualizér souběžnosti používá nastavení pro určení zásobníky volání, které jsou přidruženy údaje o výkonu.  Při zpracování trasování, přistupuje k Concurrency Visualizer symbol servery, které jsou zadány na stránce nastavení.  Při přístupu k těmto datům přes síť, zpracování trasování zpomalí.  Ke snížení množství času, které je nutné pro vyřešení symboly, můžete mezipaměti symboly místně. Pokud byly staženy symboly, Visual Studio je načíst z místní mezipaměti.  
  
## <a name="just-my-code"></a>Pouze můj kód  
 Ve výchozím nastavení je pouze můj kód sadu souborů .exe a .dll, které jsou spojeny s aktuálním řešení v sadě Visual Studio. Vizualizér souběžnosti vyhodnotí tuto sadu souborů při použití funkce pouze můj kód pro filtrování zásobníky volání. Na kartě pouze můj kód můžete přidat adresáře, které obsahují soubory .exe a .dll do umístění, která používá vizualizér souběžnosti pro pouze můj kód.  
  
 Cesty souborů .exe a .dll jsou uloženy v trasovacím souboru, když jsou shromažďována trasování.  Změna tohoto nastavení nemá vliv na všechny dříve shromážděná trasování.  
  
## <a name="buffering"></a>Ukládání do vyrovnávací paměti  
 Vizualizér souběžnosti používá trasování událostí pro Windows (ETW), když shromáždí trasování.  Trasování událostí pro Windows používá různé vyrovnávací paměti jako ukládá události.  Výchozí nastavení vyrovnávací paměti ETW nemusí být optimální ve všech případech a v některých případech, může dojít k problémům, jako je například ke ztrátě událostí.  Karta ukládání do vyrovnávací paměti ke konfiguraci nastavení vyrovnávací paměti ETW. Další informace najdete v tématu [trasování událostí](http://go.microsoft.com/fwlink/?LinkId=234579) a [EVENT_TRACE_PROPERTIES struktura](http://go.microsoft.com/fwlink/?LinkId=234580).  
  
## <a name="filter"></a>Filtr  
 Na kartě filtru můžete vybrat sadu událostí, které shromažďuje vizualizér souběžnosti. Výběrem podmnožiny události omezuje typy dat, která se zobrazí v sestavách, snižuje velikost každé trasování a snižuje dobu, které je nutné zpracovat trasování.  
  
### <a name="clr-events"></a>CLR – události  
 Události vygenerované Common Language Runtime (CLR) povolte vizualizér souběžnosti přeložit spravované zásobníky volání.  Pokud zakážete shromažďování událostí modulu CLR, zmenší velikost trasování, ale některé zásobníky volání nevyřeší.  V důsledku toho může být nesprávně kategorizovaná některé aktivita vláken procesoru.  
  
### <a name="collect-for-native-processes"></a>Shromažďování pro nativní procesy  
 Ve výchozím nastavení jsou shromažďovány události CLR jenom v případě, že je profilovaným spravovaného procesu, protože jsou obvykle není nutné, aby nativní procesy.  V některých případech (například když nativní proces je hostitelem modulu CLR) můžete chtít shromažďovat události CLR pro nativní procesu.  Pokud je to tento případ, vyberte **shromažďování pro nativní procesy** zaškrtávací políčko.  
  
### <a name="disable-rundown-events"></a>Zakázat sekvence daneho události  
 Modul CLR generuje události z dva poskytovatelé: runtime a sekvence daneho.  Pokud chcete shromáždit události modulu runtime CLR, ale chcete zamezení shromažďování sekvence daneho události, vyberte **zakázat události Rundown** zaškrtávací políčko.  Tím se snižuje velikost souboru trasování, který je generovaný kolekce, ale nemusí některé zásobníky vyřešit. Další informace najdete v tématu [CLR ETW – zprostředkovatelé](/dotnet/framework/performance/clr-etw-providers)  
  
### <a name="sample-events"></a>Ukázkové události  
 Ukázkové události můžete použít ke shromažďování zásobníky volání, které jsou přidruženy provádění vlákna. Tyto události se shromažďují přibližně jednou za milisekundu pro vláken, které jsou prováděny v aktuálním procesu. Pokud zakážete kolekce ukázkové události, se snižuje velikost shromažďovat trasování, ale nelze zobrazit žádné zásobníky volání, které jsou přidruženy provádění vlákna.  
  
### <a name="gpu-events"></a>Grafický procesor událostí  
 Grafický procesor události jsou události vygenerované DirectX. Pokud zakážete shromažďování událostí grafický procesor, se snižuje velikost shromažďovat trasování, ale žádné aktivita GPU nelze zobrazit v zobrazení využití nebo modul DirectX aktivity v zobrazení vláken.  
  
### <a name="file-io-events"></a>Vstupně-výstupní události  
 Události vstupně-výstupní soubor představují přístupů na disk jménem aktuálním procesu.  Pokud zakážete vstupně-výstupní soubor události, se snižuje velikost trasování, ale zobrazení vláken nebudou podávat žádné informace o disku kanály nebo diskových operací.  
  
## <a name="markers"></a>Značky  
 Na kartě značek můžete nakonfigurovat sadu zprostředkovatelů trasování událostí pro Windows, které jsou zobrazeny jako značky v vizualizér souběžnosti.  Můžete také filtrovat značky kolekce na základě úroveň důležitosti a kategorie trasování událostí pro Windows.  Pokud používáte [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md) a jsou pomocí vlastního zprostředkovatele značky, můžete ji zaregistrovat zde tak, aby se zobrazí v zobrazení vláken.  
  
### <a name="adding-a-new-provider"></a>Přidání nového poskytovatele  
 Pokud váš kód používá [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md) nebo generuje události trasování událostí pro Windows, které následují <xref:System.Diagnostics.Tracing.EventSource> konvence, zobrazí se tyto události v Concurrency Visualizer tak, že je zaregistrujete v tomto dialogovém.  
  
 V poli Název zadejte název, který popisuje typy událostí, které jsou generovány zprostředkovatelem.  Do pole identifikátor GUID zadejte identifikátor GUID, která souvisí s tímto poskytovatelem. (Identifikátor GUID je přidružen každých zprostředkovatel trasování událostí pro Windows.)  
  
 Volitelně můžete zadat, jestli se má filtrovat události z tohoto zprostředkovatele, podle kategorie nebo důležitost.  Můžete použít kategorii pole, které chcete filtrovat podle kategorie SDK Vizualizéru souběžnosti.  K tomu, zadejte řetězec s položkami oddělenými čárkou kategorií nebo rozsahy kategorií.  Určuje kategorie události v rámci aktuálního zprostředkovatele k zobrazení.  Chcete-li přidat <xref:System.Diagnostics.Tracing.EventSource> poskytovatele, kategorie pole můžete použít k filtrování podle klíčového slova trasování událostí pro Windows.  Klíčové slovo je bitová maska, a proto můžete zadat, které bitů v masce nastaveny řetězec celých čísel oddělených čárkou. Například "1,2" Nastaví bits první a druhý, a to znamená, že do 6 v desítkové soustavě.  
  
 V seznamu úroveň důležitosti můžete vyfiltrovat události, které mají význam nebo úroveň trasování událostí pro Windows, která je menší než zadaná hodnota.  
  
### <a name="configuring-an-existing-provider"></a>Konfigurace existujícího poskytovatele  
 Chcete-li upravit nastavení, které jsou přidruženy existujícího poskytovatele, vyberte ho v seznamu a poté zvolte **upravit poskytovatele** tlačítko.  Můžete změnit název, identifikátor GUID a filtrování nastavení.  
  
### <a name="filter-marker-data-out-of-concurrency-visualizer-reports"></a>Filtrování dat značky mimo sestavy vizualizér souběžnosti  
 Pokud nechcete, aby data pro konkrétního poskytovatele, než se objeví v budoucnosti trasování, zrušte zaškrtnutí políčka u zprostředkovatele, který chcete odebrat.  
  
## <a name="files"></a>Soubory  
 Na **soubory** kartě můžete zadat shromažďovaných adresáři, pod které trasování soubory se ukládají pokaždé, když trasování.  Vizualizér souběžnosti generuje čtyři soubory pro každý trasování, které shromáždí:  
  
-   Soubor protokolu (ETL) trasování událostí režimu jádra (*. kernel.etl)  
  
-   Soubor protokolu trasování událostí uživatelském režimu (*. user.etl)  
  
-   Soubor dat Vizualizéru souběžnosti (*. CVData)  
  
-   Soubor trasování Vizualizéru souběžnosti (*. CVTrace)  
  
 Dva soubory ETL ukládání dat trasování a dva soubory vizualizér souběžnosti uložení zpracovaná data.  Nezpracovaná souborů ETL se nepoužívají, obvykle po zpracování trasování.  Výběr **soubory odstranit událost trasování protokolu (ETL) po dokončení analýzy** políčko snižuje množství dat trasování, která je uložená na disku.  
  
## <a name="see-also"></a>Viz také  
 [Pouze můj kód](../profiling/just-my-code-threads-view.md)   
 [Značky Vizualizéru souběžnosti](../profiling/concurrency-visualizer-markers.md)