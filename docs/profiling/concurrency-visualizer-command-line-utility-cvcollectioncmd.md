---
title: Nástroj příkazového řádku ve Vizualizéru souběžnosti (CVCollectionCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.performance.cvcollectioncmd
ms.assetid: 476601be-1608-4014-af15-5aba6ccbed1c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47bd3081256ee3354b9e8fc03050570938fd7499
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2018
---
# <a name="concurrency-visualizer-command-line-utility-cvcollectioncmd"></a>Nástroj příkazového řádku Vizualizéru souběžnosti (CVCollectionCmd)
Chcete-li shromažďovat trasování z příkazového řádku, takže lze zobrazit v Concurrency Visualizer pro sadu Visual Studio můžete použít nástroj příkazového řádku Vizualizéru souběžnosti (CVCollectionCmd.exe). Nástroje lze použít v počítačích, které nemají nainstalovanou sadu Visual Studio.  
  
> [!NOTE]
>  Vizualizér souběžnosti spouštění v sadě Visual Studio 2013, je volitelné rozšíření. (Dříve se měl byl zahrnut v sadě Visual Studio.) Si můžete stáhnout [Concurrency Visualizer kolekce nástrojů pro Visual Studio 2015](http://www.microsoft.com/en-in/download/details.aspx?id=49103) z webu Stažení softwaru.  
  
## <a name="download-the-concurrency-visualizer-command-line-utility"></a>Stáhněte si nástroj příkazového řádku Vizualizéru souběžnosti  
 Chcete-li stáhnout a nainstalovat nástroj příkazového řádku, přejděte na [Concurrency Visualizer kolekce nástrojů pro Visual Studio 2015](http://www.microsoft.com/en-in/download/details.aspx?id=49103) a postupujte podle pokynů. Ve výchozím nastavení je CVCollectionCmd.exe nainstalován v %ProgramFiles%\Microsoft Concurrency Visualizer kolekce Tools\ (% ProgramFiles (x86) %\Microsoft Concurrency Visualizer kolekce Tools\ na x64 počítače).  
  
## <a name="collect-a-trace-with-cvcollectioncmd"></a>Shromažďovat trasování s CVCollectionCmd  
 Spuštěním aplikace s CVCollectionCmd nebo připojením k němu můžete shromažďovat trasování. Najdete informace o příkazech pod pro vaše možnosti. Příklad  
  
```cmd  
<Path>CVCollectionCmd /launch c:\myapp\myapp.exe /outdir c:\myapp\data  
```  
  
## <a name="commands-and-parameters"></a>Příkazy a parametry  
 K získání nápovědy o příkazech a parametry nástroj příkazového řádku, zadejte na příkazovém řádku toto:  
  
 **CvCollectionCmd /?**  
  
|Možnost|Popis|Parametry|Vrácené hodnoty|  
|------------|-----------------|----------------|-------------------|  
|Dotazy|Vrátí, zda lze spustit kolekce.|Žádné|0, pokud se kolekce můžete začít.<br /><br /> 1, pokud kolekce již probíhá.<br /><br /> 2, není-li kolekce v průběhu, ale jeden nebo více požadovaných [ETW](/dotnet/framework/wcf/samples/etw-tracing) relace je již povolen.|  
|Spuštění|Spustí proces zadaný v části vizualizér souběžnosti.|Cesta ke spustitelnému souboru.|0, pokud se úspěšně spustit.<br /><br /> 1 pro spuštění se nezdařilo, protože cílová aplikace nelze spustit.<br /><br /> 13 Pokud spustit se nezdařila, protože CVCollectionCmd nemá dostatečná oprávnění k zápisu do zadané výstupní adresář.|  
|Připojit|Začne shromažďovat trasování systémové; jinak připojí k procesu, pokud je zadaná.|Žádné|0, pokud připojení úspěšné.<br /><br /> 1, pokud připojení se nezdařila, protože zadaný proces je neplatný nebo není jednoznačná.<br /><br /> 13, pokud připojení se nezdařila, protože CVCollectionCmd nemá dostatečná oprávnění k zápisu do zadané výstupní adresář.|  
|Odpojit|Zastaví kolekce.|Žádné|0, pokud se úspěšně odpojení.<br /><br /> 1 pro odpojení se nezdařila, protože kolekce není aktuálně probíhá.<br /><br /> 2, pokud odpojení se nezdařila, protože kolekce nelze zastavit.|  
|Analyzovat|Analyzuje zadanou trasování.|Úplná cesta souboru CVTrace.|0, pokud byla analýza úspěšná.<br /><br /> 1, pokud analýza nelze spustit, protože zadaný trasování bylo systémové, ale nebyl zadán žádný cílový proces.<br /><br /> 2 Pokud analýza nelze spustit, protože trasování nebylo celý systém a proces byl zadán.<br /><br /> 3 Pokud analýza se nezdařila, protože určený proces je neplatný.<br /><br /> 4, pokud analýza se nezdařila, protože zadaný soubor CVTrace je neplatný.|  
|LaunchArgs|Určuje argumenty spustitelné cíl. Tato možnost se vztahuje na příkaz spustit.|Argumenty příkazového řádku k aplikaci.|Žádné|  
|OutDir|Určuje adresář, do které uložíte trasovací soubory. Platí pro příkazy spouštěcí a připojit.|Cesta k adresáři nebo relativní cestu.|Žádné|  
|Proces|Určuje proces pro připojení k provedení příkazu připojit nebo proces v trasování pro analýzu, když se spustí příkaz analyzovat. Platí pro příkazy připojit a analyzovat.|Název procesu nebo PID.|Žádné|  
|Konfigurace|Určuje cestu konfiguračního souboru, pokud chcete nastavení kolekce než výchozí hodnoty.   Platí pro spuštění, připojit a analyzovat příkazy.|Cesta k adresáři nebo relativní cesta ke konfiguračnímu souboru XML.|Žádné|  
  
## <a name="customizing-configuration-settings"></a>Přizpůsobení nastavení konfigurace  
 Pokud používáte CVCollectionCmd shromažďovat trasování a chcete přizpůsobit nastavení kolekce a potom zadejte je pomocí konfiguračního souboru.  
  
> [!NOTE]
>  Pokud používáte Visual Studio shromažďovat trasování, přímo neupravujte konfiguračního souboru.  Místo toho použijte [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialogové okno Upravit nastavení.  
  
 Pokud chcete upravit nastavení kolekce, vytvořte soubor konfigurace na počítači, kde budete spouštět nástroj CVCollectionCmd. Konfigurační soubor můžete vytvořit od začátku, nebo můžete upravit a zkopírujte konfigurační soubor na počítači, který má nainstalovanou sadu Visual Studio. Název souboru `UserConfig.xml` a nachází se v **místní data aplikací** složky. Pokud spustíte nástroj, pomocí možnosti konfigurace ve spojení s příkaz spuštění, připojit nebo analyzovat.  V parametru, který je spojen s možností konfigurace zadejte cestu k souboru konfigurace.  
  
### <a name="configuration-file-tags"></a>Konfigurace souboru značky  
 Konfigurační soubor je založený na jazyce XML. Zde jsou platné značky a hodnoty:  
  
|Značka|Popis|Hodnoty|  
|---------|-----------------|------------|  
|Konfigurace|Vymezuje pásma celkové konfiguračním souboru.|Musí obsahovat tyto prvky:<br /><br /> -MinorVersion<br />-MajorVersion|  
|MajorVersion|Určuje hlavní verzi do konfiguračního souboru.|Musí být 1 pro [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projekty. Pokud není nástroj 1, nebude fungovat.|  
|MinorVersion|Určuje dílčí verze konfiguračního souboru.|Musí být 0 pro [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projekty. Pokud není nástroj 0, nebudou fungovat.|  
|IncludeEnvSymbolPath|Nastaví hodnotu, která určuje, zda je cesta symbol prostředí (_NT_SYMBOL_PATH) používá.|-True<br />-False|  
|DeleteEtlsAfterAnalysis|Nastaví hodnotu, která určuje, zda jsou odstraněny soubory ETL po dokončení analýzy.|-True<br />-False|  
|Symbolpath –|Určuje cestu k serveru symbol. Další informace najdete v tématu [používat Microsoft Symbol Server získat soubory se symboly ladění](http://go.microsoft.com/fwlink/?LinkID=149389).|Název adresáře nebo adresa URL.|  
|Značky|Obsahuje seznam zprostředkovatelů značky.|Může obsahovat nula nebo více MarkerProvider prvků.|  
|MarkerProvider|Určuje zprostředkovatele jednu značku.|Musí obsahovat tyto prvky:<br /><br /> -Úroveň<br />-GUID<br />-Název<br /><br /> Může obsahovat tyto prvky:<br /><br /> -Kategorií<br />-Hodnotu IsEnabled|  
|úroveň|Nastaví úroveň důležitosti MarkerProvider.|-Nízká<br />-Normální<br />-Vysoká<br />-Kritické<br />-Vše|  
|Identifikátor GUID|Globálně jedinečný identifikátor značky zprostředkovatele trasování událostí pro Windows.|IDENTIFIKÁTOR GUID.|  
|Název|Určuje popis zprostředkovatele značky.|Řetězec.|  
|Kategorie|Určuje kategorie shromážděné pro zprostředkovatele značky.|Řetězec s položkami oddělenými čárkou čísla nebo rozsahy čísel.|  
|Hodnotu IsEnabled|Nastaví hodnotu, která určuje, zda zprostředkovatel značky je povoleno pro kolekci.|-True<br />-False|  
|FilterConfig|Určuje seznam možností konfigurace událostí trasování událostí pro Windows, které jsou filtrovány z kolekce.|Může obsahovat tyto prvky:<br /><br /> -CollectClrEvents<br />-ClrCollectionOptions<br />-CollectSampleEvents<br />-CollectGpuEvents<br />-CollectFileIO|  
|CollectClrEvents|Nastaví hodnotu, která určuje, zda jsou shromažďovány události CLR.|-True<br />-False|  
|ClrCollectionOptions|Určuje, zda se mají shromažďovat události CLR pro nativní aplikace a zda se mají shromažďovat NGEN sekvence daneho události.|Může obsahovat jednu, oba nebo žádná z těchto hodnot:<br /><br /> -CollectForNative<br />-DisableNGenRundown|  
|CollectSampleEvents|Nastaví hodnotu, která určuje, zda jsou shromažďovány ukázkové události.|-True<br />-False|  
|CollectGpuEvents|Nastaví hodnotu, která určuje, zda jsou shromažďovány události generované objektem Directx.|-True<br />-False|  
|CollectFileIO|Nastaví hodnotu, která určuje, zda jsou shromažďovány události vstupně-výstupní.|-True<br />-False|  
|UserBufferSettings|Určuje seznam parametrů vyrovnávací paměti – nastavení uživatele.|Musí obsahovat tyto prvky:<br /><br /> -BufferFlushTimer<br />-BufferSize<br />-MinimumBuffers<br />-MaximumBuffers|  
|KernelBufferSettings|Určuje seznam parametrů nastavení vyrovnávací paměti jádra.|Musí obsahovat tyto prvky:<br /><br /> -BufferFlushTimer<br />-BufferSize<br />-MinimumBuffers<br />-MaximumBuffers|  
|BufferFlushTimer|Určuje časovač vyprázdnění vyrovnávacích pamětí trasování událostí pro Windows.|Kladné celé číslo.|  
|BufferSize|Množství paměti přidělené pro každé vyrovnávací paměti události trasování relace, v kilobajtech.|Číslo od 0 do 1024.|  
|MinimumBuffers|Minimální počet vyrovnávacích pamětí, které jsou přiděleny pro fond vyrovnávací paměti relace trasování událostí.|Kladné celé číslo větší než nebo rovna hodnotě dvojnásobný počet logických jader.|  
|MaximumBuffers|Maximální počet vyrovnávacích pamětí, které jsou přiděleny pro fond vyrovnávací paměti relace trasování událostí.|Číslo větší než nebo rovna hodnotě MinimumBuffers.|  
|JustMyCode|Určuje seznam adresářů pouze můj kód.|Seznam počtu nula či více elementů MyCodeDirectory.|  
|MyCodeDirectory|Určuje adresář, který obsahuje váš kód.|Absolutní cesta.|  
  
### <a name="example"></a>Příklad  
 Místo vytvoření konfiguračního souboru od začátku, můžete zkopírovat následující příklad a upravit ho, aby splňovaly vaše požadavky.  
  
```xml  
<?xml version="1.0"?>  
<LocalConfig xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" MajorVersion="1" MinorVersion="0">  
  
  <IncludeEnvSymbolPath>true</IncludeEnvSymbolPath>  
  
  <DeleteEtlsAfterAnalysis>true</DeleteEtlsAfterAnalysis>  
  
  <TraceLocation>C:\traces</TraceLocation>  
  
  <SymbolPath>http://symweb</SymbolPath>  
  
  <Markers>  
    <MarkerProvider Name="Default" Guid="8d4925ab-505a-483b-a7e0-6f824a07a6f0" Level="Low" />  
    <MarkerProvider Name="TPL" Guid="2e5dba47-a3d2-4d16-8ee0-6671ffdcd7b5" Level="Normal" />  
    <MarkerProvider Name="TPL Dataflow" Guid="16f53577-e41d-43d4-b47e-c17025bf4025" Level="Normal" />  
    <MarkerProvider Name="TPL Synchronization" Guid="ec631d38-466b-4290-9306-834971ba0217" Level="Normal" />  
    <MarkerProvider Name="PLINQ" Guid="159eeeec-4a14-4418-a8fe-faabcd987887" Level="Normal" />  
    <MarkerProvider Name="Concurrency Runtime" Guid="f7b697a3-4db5-4d3b-be71-c4d284e6592f" Level="Normal" />  
    <MarkerProvider Name="Scenario Markers" Guid="fb9244c9-f23a-4966-8a9c-97a51f8c355b" Level="Low" />  
  
    <!-- The IsEnabled and Categories elements are optional -->  
    <MarkerProvider Name="myMarker1" Guid="d0dbb3a3-895c-4ce6-96d9-28f69d664dc3" Level="Critical" IsEnabled="false" Categories="0,1,3-5,8" />  
    <MarkerProvider Name="myMarker2" Guid="03452127-a617-4302-9e30-c0d10442e4ee" Level="Low" IsEnabled="false" Categories="0,1,3-5,8-10,11-13" />  
  </Markers>  
  
  <FilterConfig>  
    <CollectClrEvents>true</CollectClrEvents>  
    <ClrCollectionOptions>CollectForNative DisableNGenRundown</ClrCollectionOptions>  
    <CollectSampleEvents>true</CollectSampleEvents>  
    <CollectGpuEvents>true</CollectGpuEvents>  
    <CollectFileIO>true</CollectFileIO>  
  </FilterConfig>  
  
  <UserBufferSettings>  
    <BufferFlushTimer>0</BufferFlushTimer>  
    <BufferSize>256</BufferSize>  
    <MinimumBuffers>512</MinimumBuffers>  
    <MaximumBuffers>1024</MaximumBuffers>  
  </UserBufferSettings>  
  
  <KernelBufferSettings>  
    <BufferFlushTimer>0</BufferFlushTimer>  
    <BufferSize>256</BufferSize>  
    <MinimumBuffers>512</MinimumBuffers>  
    <MaximumBuffers>1024</MaximumBuffers>  
  </KernelBufferSettings>  
  
  <!-- List of MyCodeDirectory directories -->  
  <JustMyCode>  
    <MyCodeDirectory>C:\myBinaries1</MyCodeDirectory>  
    <MyCodeDirectory>C:\myBinaries2</MyCodeDirectory>  
  </JustMyCode>  
</LocalConfig>  
  
```
