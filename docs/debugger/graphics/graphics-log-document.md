---
title: Grafika protokolu dokumentu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.vsglog.error
- vs.graphics.experiment
- vs.graphics.vsglog
ms.assetid: 6ccb1269-d55f-49c4-920d-baedf7de2888
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 772287d31a3428c3791ead08103f2318763e1701
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="graphics-log-document"></a>Dokument grafických protokolů
Dokument grafických protokolů je záznam grafiky události, které došlo k chybě aplikace byla spuštěna v rámci relace diagnostiky grafiky. Po zapsání můžete zkontrolovat protokol ve Visual Studio Graphics Analyzer k diagnostikování problémů vykreslování a výkonu.  
  
 Toto je co dokument grafických protokolů vypadá jako v analyzátoru grafiky:  
  
 ![Grafika protokol, který obsahuje dva zaznamenané rámce. ] (media/gfx_diag_demo_graphics_log_orientation.png "gfx_diag_demo_graphics_log_orientation")  
  
## <a name="understanding-graphics-log-documents"></a>Principy grafiky protokolu dokumenty  
 Pomocí analyzátor grafiky Prozkoumat dokument grafických protokolů můžete vizualizovat důsledky Direct3D – události v cíli vykreslování, které došlo během zachycení. Lze přesně určit oblasti vykreslení cíle, které obsahují neočekávané výstup. Když vyberete jeden bod v ovlivněných oblasti, můžete zkontrolovat, jeho shadery, Direct3D – události, které se vztahuje, zásobník volání aplikace, která vedla k události a objekty rozhraní DirectX, které podporují tyto události diagnostiky grafiky. Tyto informace můžete použít k diagnostikování problémů vykreslování v hry nebo aplikace.  
  
 Horní části okna (**Experiment.vsglog grafiky**) zobrazí aktuální vykreslení cílový výstup vybraný snímek a v dolní části se zobrazí **rámce seznamu** obsahující obrázky miniatur zaznamenané rámce.  
  
#### <a name="to-inspect-a-frame"></a>Chcete-li prověřit rámeček  
  
-   V **rámce seznamu**, vyberte rámce, který chcete zkontrolovat. Cílový výstup vykreslení v horní části dokument grafických protokolů se aktualizuje a zobrazí vybraný snímek.  
  
#### <a name="to-inspect-a-pixel"></a>Chcete-li prověřit pixel  
  
-   V horní části dokument grafických protokolů vyberte z výstupu cíl vykreslení pixelů, který chcete. Pokud je vybraný jeden bod, můžete použít **historie pixelů grafiky** okno Chcete-li zobrazit podrobné informace o vybrané pixelů. Další informace najdete v tématu [historie pixelu](graphics-pixel-history.md).  
  
## <a name="playback-machine"></a>Počítače pro přehrávání  
 Zobrazí také v pravém horním rohu **rámce seznamu** je **počítače pro přehrávání**. Počítače pro přehrávání je počítač nebo zařízení, která se používá k přehrání událostí grafiky ze souboru protokolu grafiky během novější relace diagnostiky grafiky. Pomocí jiného zařízení místo vývojovém počítači přehrát zaznamenané události, přesněji znovu vyvolali spuštění prostředí, ve které k problému dochází – například můžete použít počítač, který má jinou grafiky hardware nebo ovladače než ty, které používá vývojovém počítači, nebo jiné typy zařízení, například na bázi ARM Windows RT tablet nebo zařízení Windows Phone.  
  
 Informace o tom, jak určit počítače pro přehrávání najdete v tématu [postupy: Změna počítače pro přehrávání diagnostiky grafiky](how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="graphics-log-summary-information"></a>Souhrnné informace protokolu grafiky  
 Když soubor protokolu grafika je aktivní dokument **vlastnosti** okno zobrazuje informace o prostředí, jehož hostitelem relace zachycení diagnostiky grafiky. Se zobrazí několik kategorií informace.  
  
 **Direct3D – informace**  
 Zobrazí informace o hardwaru a ovladačů funkce grafický adaptér, který byl použitý při relaci zachytávání.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Formát vysoké barvy XR 10-bit**|**Hodnota TRUE,** Pokud 10 bitů XR vysokou color formát je podporované, jinak hodnota **False**.|  
|**DirectCompute CS 4.x**|**Hodnota TRUE,** Pokud výpočetní shaderu 4.0 je podporované, jinak hodnota **False**.|  
|**Dvojité přesnosti shadery**|**Hodnota TRUE,** Pokud hodnoty s plovoucí desetinnou čárkou (64 bitů) Dvojitá přesnost, podporuje grafický adaptér, jinak hodnota **False**.|  
|**Zobrazí příkaz ovladačů**|**Hodnota TRUE,** Pokud ovladač podporuje seznamy příkaz; jinak **False**.|  
|**Vytvoří souběžných ovladačů**|**Hodnota TRUE,** Pokud ovladač podporuje souběžné vytvoření (asynchronní); jinak **False**.|  
|**Rozšířené formáty (BGRA atd.)**|**Hodnota TRUE,** Pokud rozšířené formátů, jako BGRA jsou podporované, jinak hodnota **False**.|  
|**Funkce HW maximální úroveň**|Zobrazí na nejvyšší úrovni funkce, který podporuje grafický adaptér.|  
  
 **Zobrazení informací**  
 Zobrazí informace o grafický adaptér, který byl použitý při relaci zachytávání.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Popis**|Řetězec zobrazení Popis adaptéru.|  
|**Zobrazovací paměti**|Množství paměti, který je nainstalován na grafickému adaptéru.|  
|**Název ovladače**|Název ovladače grafického adaptéru.|  
|**Verze ovladače**|Verze ovladače grafického adaptéru.|  
|**Jméno**|Název grafickému adaptéru.|  
  
 **Soubor experimentu**  
 Uvádí informace o souboru experimentu, který je spojen s relaci zachytávání.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Cesta**|Cesta souboru .vsglog. **Poznámka:** pod starší verze zachycení, tato vlastnost se nepoužívá.|  
  
 **Informace o modulu**  
 Obsahuje název a verzi dynamické knihovny (DLL), které byly načteny aplikace během relaci zachytávání.  
  
 **Informace o systému**  
 Uvádí informace o hardwaru a operačního systému, který hostuje aplikaci během relace zachytávání.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Paměť**|Množství paměti, který je nainstalován v počítači.|  
|**Architektura operačního systému**|Cíl architektura procesoru operačního systému.|  
|**Verze operačního systému**|Verze operačního systému.|  
|**Procesor**|Procesor, který je nainstalován v počítači.|  
|**Architektura cílové aplikace**|Cíl architektura procesoru aplikace. To může být jiná než **architekturu OS**.|  
  
 **Cílové aplikace**  
 Zobrazí informace o aplikaci, která je předmětem relaci zachytávání.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Datum a čas poslední úpravy**|Datum a čas, který byl postavený na aplikaci.|  
|**Cesta**|Cesta k aplikaci.|  
|**ID procesu**|ID procesu, který byl zadán pro aplikaci.|  
|**Verze**|Verze aplikace.|  
  
 **Soubor protokolu VSG**  
 Zobrazí informace o dokument grafických protokolů.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Autor**|Název aplikace, kterou vytvořili grafiky protokolu dokumentu. Například, pokud bylo inicializováno relaci zachytávání [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (ruční zachytávání) hodnota této vlastnosti je [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|  
|**Čas spuštění relace**|Datum a čas zahájení relaci zachytávání.|  
|**Velikost**|Velikost dokument grafických protokolů.|  
  
## <a name="see-also"></a>Viz také  
 [Návod: Chybějící objekty z důvodu použití funkce Vertex Shading](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [Návod: Ladění chyb při vykreslování způsobených stínováním](walkthrough-debugging-rendering-errors-due-to-shading.md)