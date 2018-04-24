---
title: Vsinstr – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, instrumentation
- instrumentation, VSInstr tool
- profiling tools,VSInstr
- command-line tools, instrumentation
- command line, tools
- VSInstr
- VSInstr tool
- performance tools, VSInstr tool
ms.assetid: 7b1334f7-f9b0-4a82-a145-d0607bfa8467
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64e9d8c2b25d779bfe0e80aa7b7d324f7a69879c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="vsinstr"></a>VSInstr
Vsinstr – nástroj slouží k instrumentace binárních souborů. Je možné pomocí následující syntaxe:  
  
```  
VSInstr [/U] filename [/options]  
```  
  
 Následující tabulka popisuje možnosti vsinstr – nástroj:  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**Pomůže** nebo **?**|Zobrazí nápovědu.|  
|**U**|Zapíše výstup přesměrovaného konzoly jako kódování Unicode. Musí být zadána první možnost.|  
|`@filename`|Určuje název souboru odpovědí, který obsahuje jeden příkazového řádku na každém řádku.  Nepoužívejte uvozovky.|  
|**OutputPath** `:path`|Určuje cílový adresář instrumentovaného bitové kopie. Pokud není zadaná výstupní cesta, původní binární přejmenován připojením "Orig" k názvu souboru ve stejném adresáři a je instrumentovány kopii binárního souboru.|  
|**Vyloučení** `:funcspec`|Určuje funkce specifikace chcete vyloučit z instrumentace podle sondy. Je užitečná při profilace vložení testu ve funkci způsobí, že nepředvídatelným nebo nežádoucí výsledky.<br /><br /> Nepoužívejte **vyloučit** a **zahrnout** možnosti, které odkazují na funkce ve stejném binárního souboru.<br /><br /> Můžete zadat několik specifikace funkce samostatné **vyloučit** možnosti.<br /><br /> `funcspec` je definované jako:<br /><br /> [obor názvů\<separator1 >] [třída\<separator2 >] – funkce<br /><br /> \<separator1 > je `::` pro nativní kód a `.` pro spravovaný kód.<br /><br /> \<separator2 > je vždy `::`<br /><br /> **Vyloučit** jsou podporovány pro pokrytí kódu.<br /><br /> Zástupný znak \* je podporována. Chcete-li například vyloučit všechny funkce v oboru názvů používají:<br /><br /> MyNamespace::\*<br /><br /> Můžete použít **vsinstr – /DumpFuncs** seznam dokončení názvy funkcí v zadané binárního souboru.|  
|**Zahrnout** `:funcspec`|Určuje funkce specifikace v binární účelem instrumentace s testy paměti. Všechny funkce v binární soubory nejsou instrumentovány.<br /><br /> Můžete zadat několik specifikace funkce samostatné **zahrnout** možnosti.<br /><br /> Nepoužívejte **zahrnout** a **vyloučit** možnosti, které odkazují na funkce ve stejném binárního souboru.<br /><br /> **Zahrnout** není podporovaný s pokrytí kódu.<br /><br /> `funcspec` je definované jako:<br /><br /> [obor názvů\<separator1 >] [třída\<separator2 >] – funkce<br /><br /> \<separator1 > je `::` pro nativní kód a `.` pro spravovaný kód.<br /><br /> \<separator2 > je vždy `::`<br /><br /> Zástupný znak \* je podporována. Chcete-li například zahrnout všechny funkce v oboru názvů používají:<br /><br /> MyNamespace::\*<br /><br /> Můžete použít **vsinstr – /DumpFuncs** seznam dokončení názvy funkcí v zadané binárního souboru.|  
|**DumpFuncs**|Obsahuje seznam funkcí v rámci zadanou bitovou kopii. Neprobíhá žádná instrumentace.|  
|**ExcludeSmallFuncs**|Vyloučí malé funkce, které jsou krátkých funkcí, které neprovádějte žádné volání funkcí, z instrumentace. **ExcludeSmallFuncs** poskytuje možnost pro menší nároky na instrumentace se proto vylepšené instrumentace rychlostí.<br /><br /> Vyloučení malé funkce taky snižuje velikost souboru .vsp a čas potřebný pro analýzu.|  
|**Označit:**{**před**`&#124;`**po**`&#124;`**horní**`&#124;`**dolní**}`,funcname,markid`|Vloží značku profilu (identifikátor používaný k oddělení dat v sestavách), můžete použít k identifikaci počáteční nebo koncový rozsahu dat v souboru .vsp sestavy.<br /><br /> **Před** – bezprostředně před vstupem funkce cíl.<br /><br /> **Po** – ihned po ukončení funkce cíl.<br /><br /> **Horní** – bezprostředně po zadání cílové funkce.<br /><br /> **Dolní** – bezprostředně před každou vrátit ve funkci cíl.<br /><br /> `funcname` -Název funkce cíl<br /><br /> `Markid` -Kladné celé číslo (long) chcete použít jako identifikátor značky profilu.|  
|**Pokrytí**|Provede pokrytí instrumentace. Dá se dá použít jenom s následující možnosti: **podrobné**, **OutputPath**, **vyloučit**, a **Logfile**...|  
|**Verbose**|**Podrobné**možnost se používá k zobrazení podrobných informací o procesu instrumentace.|  
|**NoWarn** `[:[Message Number[;Message Number]]]`|Potlačit všechny nebo konkrétní varování.<br /><br /> `Message Number` -počet upozornění. Pokud `Message Number` je tento parametr vynechán, jsou potlačeny všechny výstrahy.<br /><br /> Další informace najdete v tématu [upozornění VSInstr](../profiling/vsinstr-warnings.md).|  
|**Ovládací prvek** `:{` **vláken** `&#124;` **proces** `&#124;` **globální** `}`|Určuje úroveň profilování následující shromažďování dat vsinstr – řízení možností:<br /><br /> **Start**<br /><br /> **StartOnly**<br /><br /> **Pozastavit**<br /><br /> **StopOnly**<br /><br /> **SuspendOnly**<br /><br /> **ResumeOnly**<br /><br /> **Vlákno** -určuje funkce řízení kolekce dat úrovni přístup z více vláken. Profilace je spustit nebo zastavit pouze pro aktuální vlákno. Profilování stav jiná vlákna nemá vliv. Výchozí hodnota je přístup z více vláken.<br /><br /> **Proces** -určuje funkce ovládacího prvku kolekce profilování data úrovni procesu. Profilace spuštění nebo zastavení pro všechna vlákna v aktuálním procesu. Profilování stav jiné procesy nemá vliv.<br /><br /> **Globální** -určuje funkce řízení kolekce dat (mezi procesy) globální úrovni.<br /><br /> Pokud nezadáte úroveň profilování dojde k chybě.|  
|**Spustit** `:{` **uvnitř** `&#124;` **mimo** `},funcname`|Omezení shromažďování dat funkce cíl a podřízené funkce volané pomocí této funkce.<br /><br /> **Uvnitř** -vloží funkci StartProfile bezprostředně po zadání cílové funkce. Vloží funkci StopProfile bezprostředně před každou vrátit ve funkci cíl.<br /><br /> **Mimo** -vloží funkci StartProfile bezprostředně před každou volání funkce cíl. Vloží funkci StopProfile ihned po každém volání funkce cíl.<br /><br /> `funcname` -název funkce cíl.|  
|**Pozastavit** `:{` **uvnitř** `&#124;` **mimo** `},funcname`|Vyloučí shromažďování dat pro cílový funkce a funkce podřízené volané funkce.<br /><br /> **Uvnitř** -vloží funkci SuspendProfile bezprostředně po zadání cílové funkce. Vloží funkci ResumeProfile bezprostředně před každou vrátit ve funkci cíl.<br /><br /> **Mimo** -vloží funkci SuspendProfile bezprostředně před vstupem funkce cíl. Vloží funkci ResumeProfile ihned po ukončení z funkce cíl.<br /><br /> `funcname` -název funkce cíl.<br /><br /> Pokud cílový funkce obsahuje StartProfile funkce, funkce SuspendProfile vložena před ním. Pokud cílový funkce obsahuje StopProfile funkce, funkce ResumeProfile vložena za ním.|  
|**StartOnly:** `{` **před** `&#124;` **po** `&#124;` **horní** `&#124;` **dolní** `},funcname`|Začne shromažďování dat během spuštění profilování. Funkce rozhraní StartProfile API vloží do zadaného umístění.<br /><br /> **Před** – bezprostředně před vstupem funkce cíl.<br /><br /> **Po** – ihned po ukončení funkce cíl.<br /><br /> **Horní** – bezprostředně po zadání cílové funkce.<br /><br /> **Dolní** – bezprostředně před každou vrátit ve funkci cíl.<br /><br /> `funcname` -název funkce cíl.|  
|**StopOnly:**{**před**`&#124;`**po**`&#124;`**horní**`&#124;`**dolní**}`,funcname`|Zastaví shromažďování dat během spuštění profilování. Vloží funkci StopProfile do zadaného umístění.<br /><br /> **Před** – bezprostředně před vstupem funkce cíl.<br /><br /> **Po** – ihned po ukončení funkce cíl.<br /><br /> **Horní** – bezprostředně po zadání cílové funkce.<br /><br /> **Dolní** – bezprostředně před každou vrátit ve funkci cíl.<br /><br /> `funcname` -název funkce cíl.|  
|**SuspendOnly:**{**před**`&#124;`**po**`&#124;`**horní**`&#124;`**dolní**}`,funcname`|Zastaví shromažďování dat během spuštění profilování. Rozhraní API SuspendProfile vloží do zadaného umístění.<br /><br /> **Před** – bezprostředně před vstupem funkce cíl.<br /><br /> **Po** – ihned po ukončení funkce cíl.<br /><br /> **Horní** – bezprostředně po zadání cílové funkce.<br /><br /> **Dolní** – bezprostředně před každou vrátit ve funkci cíl.<br /><br /> `funcname` -název funkce cíl.<br /><br /> Pokud cílový funkce obsahuje StartProfile funkce, funkce SuspendProfile vložena před ním.|  
|**ResumeOnly:**{**před**`&#124;`**po**`&#124;`**horní**`&#124;`**dolní**}`,funcname`|Začíná nebo obnoví shromažďování dat během spuštění profilování.<br /><br /> Zpravidla se používá ke spuštění profilování po **SuspendOnly** možnost byla zastavena profilace. Rozhraní API ResumeProfile vloží do zadaného umístění.<br /><br /> **Před** – bezprostředně před vstupem funkce cíl.<br /><br /> **Po** – ihned po ukončení funkce cíl.<br /><br /> **Horní** – bezprostředně po zadání cílové funkce.<br /><br /> **Dolní** – bezprostředně před každou vrátit ve funkci cíl.<br /><br /> `funcname` -název funkce cíl.<br /><br /> Pokud cílový funkce obsahuje StopProfile funkce, funkce ResumeProfile vložena za ním.|  
  
## <a name="see-also"></a>Viz také  
 [Vsperfmon –](../profiling/vsperfmon.md)   
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Vsperfreport –](../profiling/vsperfreport.md)   
 [Upozornění VSInstr](../profiling/vsinstr-warnings.md)   
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)