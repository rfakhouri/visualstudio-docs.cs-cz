---
title: Dokumentu protokolu grafiky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.graphics.vsglog.error
- vs.graphics.experiment
- vs.graphics.vsglog
ms.assetid: 6ccb1269-d55f-49c4-920d-baedf7de2888
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aed2acd4dbf921d99bcefe2e74575401fc01c7d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62895977"
---
# <a name="graphics-log-document"></a>Dokument grafických protokolů
Dokumentu protokol grafiky je záznam událostí grafiky, ke kterým došlo, když byla aplikace spuštěna v rámci relace diagnostiky grafiky. Po zapsání můžete prozkoumat v protokolu ve Visual Studio Graphics Analyzer k diagnostice problémů vykreslování a výkonu.

 Toto je co dokument grafických protokolů vypadá podobně jako v analyzátoru grafiky:

 ![Protokol grafiky obsahuje dva zachycené snímky. ](media/gfx_diag_demo_graphics_log_orientation.png "gfx_diag_demo_graphics_log_orientation")

## <a name="understanding-graphics-log-documents"></a>Vysvětlení grafiky protokolu dokumenty
 Pomocí analyzátoru grafiky sady k prozkoumání dokument grafických protokolů můžete sledovat účinky událostmi rozhraní Direct3D na cíl vykreslování, ke které došlo při zachytávání. Můžete určit oblasti cíle vykreslování, které obsahují neočekávaný výstup. Když vyberte pixel v ovlivněné oblasti, můžete ke kontrole, jeho shadery, události rozhraní Direct3D, které měla vliv na to, zásobník volání aplikace, která vedla k těmto událostem a objekty rozhraní DirectX, které podporují tyto události modulu Diagnostika grafiky. Tyto informace můžete použít k diagnostice problémů vykreslování ve hře nebo aplikaci.

 Horní část okna (**grafiky Experiment.vsglog**) zobrazí aktuální výstup cíle vykreslení vybraného snímku a v dolní části zobrazují **seznam snímků** obsahující obrázky miniatur zachycené snímky.

#### <a name="to-inspect-a-frame"></a>Chcete-li prověřit blok

- V **seznam snímků**, vyberte snímek, který chcete zkontrolovat. Výstup cíle vykreslení v horní části dokumentu protokol grafiky se aktualizuje a zobrazí vybraný rámec.

#### <a name="to-inspect-a-pixel"></a>Chcete-li prověřit pixel

- V horní části dokumentu protokol grafiky vyberte pixel, který chcete výstup cíle vykreslení. Když je vybraný pixel, můžete **historie pixelů grafiky** okno k zobrazení podrobných informací o vybraný pixel. Další informace najdete v tématu [historie pixelů](graphics-pixel-history.md).

## <a name="playback-machine"></a>Počítač pro přehrávání
 Zobrazí také v pravém horním rohu **seznam snímků** je **počítač pro přehrávání**. Počítač pro přehrávání je počítač nebo zařízení, které slouží k přehrání událostí grafiky z grafického protokolu souboru během novější relace diagnostiky grafiky. Pomocí jiného zařízení místo svého vývojového počítače k přehrání zachycené události může přesněji reprodukovat spouštěcí prostředí, ve kterém dochází k problému – například můžete použít počítač, který má jiný grafický hardware nebo ovladače než ty, které používá vývojovém počítači, nebo jiných typů zařízení, například tablety Windows RT založené na ARM nebo zařízení Windows Phone.

 Informace o tom, jak určit počítač pro přehrávání, naleznete v tématu [jak: Změnit počítač pro přehrávání diagnostiky grafiky](how-to-change-the-graphics-diagnostics-playback-machine.md).

## <a name="graphics-log-summary-information"></a>Souhrnné informace protokolu grafiky
 Když soubor protokolu grafiky je aktivní dokument **vlastnosti** okno zobrazuje informace o prostředí, jehož hostitelem relace zachycení diagnostiky grafiky. Zobrazí se několik kategorií informací.

 **Informace o rozhraní Direct3D** informacemi o funkcí hardwaru a ovladače grafického adaptéru, který se používá během relace zachytávání.

|Vlastnost|Popis|
|--------------|-----------------|
|**Formát High Color 10-bit XR**|**Hodnota TRUE** Pokud 10-bit XR high color formát je podporovaná; v opačném případě **False**.|
|**DirectCompute CS 4.x**|**Hodnota TRUE** Pokud výpočetní Shader 4.0 je podporovaná; v opačném případě **False**.|
|**Shadery dvojnásobné přesnosti**|**Hodnota TRUE** Pokud grafický adaptér podporuje dvojité přesnosti s plovoucí desetinnou čárkou hodnoty (64 bitů); v opačném případě **False**.|
|**Seznamy příkazů ovladače**|**Hodnota TRUE** Jestliže ovladač podporuje seznamy příkazů; v opačném případě **False**.|
|**Souběžné produkty ovladače**|**Hodnota TRUE** Jestliže ovladač podporuje souběžné vytvoření (asynchronní); v opačném případě **False**.|
|**Rozšířené formáty (BGRA atd.)**|**Hodnota TRUE** Pokud rozšířené formátech, jako jsou BGRA jsou podporované; v opačném případě **False**.|
|**Úroveň hardwarové výbavy Max**|Zobrazí nejvyšší úroveň funkce, který podporuje grafický adaptér.|

 **Zobrazení informací** informacemi o grafický adaptér, který se používá během relace zachytávání.

|Vlastnost|Popis|
|--------------|-----------------|
|**Popis**|Zobrazovaný řetězec popis adaptéru.|
|**Zobrazení paměti**|Velikost paměti, která je nainstalovaná na grafický adaptér.|
|**Název ovladače**|Název ovladače grafického adaptéru.|
|**Verze ovladače**|Verze ovladače grafického adaptéru.|
|**Název**|Název grafického adaptéru.|

 **Experimentujte souboru** uvádí informace o souboru experiment, který je spojen s relace zachytávání.

|Vlastnost|Popis|
|--------------|-----------------|
|**Cesta**|Cestu k souboru .vsglog. **Poznámka:**  V rámci starší verze zachycení tato vlastnost se nepoužívá.|

 **Informace o modulu** se zobrazuje název a verze dynamické knihovny (DLL), která byla načtena aplikace během relace zachycení.

 **Informace o systému** uvádí informace o hardwaru a operačního systému, který je hostitelem aplikace během relace zachycení.

|Vlastnost|Popis|
|--------------|-----------------|
|**Paměť**|Množství paměti, která je nainstalována v počítači.|
|**Architektura operačního systému**|Cílové architektury procesoru operačního systému.|
|**Verze operačního systému**|Verze operačního systému.|
|**Procesor**|Procesor, který je nainstalován v počítači.|
|**Architektura cílové aplikace**|Cílové architektuře procesoru v aplikaci. To může být jiné než **Architektura operačního systému**.|

 **Cílová aplikace** uvádí informace o aplikaci, která je předmětem relace zachytávání.

|Vlastnost|Popis|
|--------------|-----------------|
|**Datum/čas poslední změny**|Datum a čas, kterou byla aplikace vytvořena.|
|**Cesta**|Cesta aplikace.|
|**ID procesu**|ID procesu, který byl zadán pro aplikaci.|
|**Verze**|Verze aplikace.|

 **Soubor protokolu VSG** uvádí informace o dokumentu protokol grafiky.

| Vlastnost | Popis |
|------------------------| - |
| **Vytvořil** | Název aplikace, kterou vytvořili grafiky protokolu dokumentu. Například, pokud byla relace zachytávání iniciovaná [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (ruční capture) hodnota této vlastnosti je [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. |
| **Čas spuštění relace** | Datum a čas zahájení relace zachytávání. |
| **Velikost** | Velikost dokument grafických protokolů. |

## <a name="see-also"></a>Viz také
- [Návod: Chybějící objekty kvůli vertex shaderu](walkthrough-missing-objects-due-to-vertex-shading.md)
- [Návod: Ladění chyb při vykreslování, které jsou způsobené stínováním](walkthrough-debugging-rendering-errors-due-to-shading.md)