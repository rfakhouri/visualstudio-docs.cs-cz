---
title: "Popis Directory šablony (. Soubory VSDIR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .vsdir files
- VSDIR files
- template directory description files
ms.assetid: 9df51800-190e-4662-b685-fdaafcff1400
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 739dd0d41fb63c4993dad0d66737aaada1cf01c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="template-directory-description-vsdir-files"></a>Popis Directory šablony (. Soubory VSDIR)
Soubor popisu directory šablony (.vsdir) je textový soubor, který umožňuje integrované vývojové prostředí (IDE) k zobrazení složky, průvodce .vsz soubory a soubory šablony, které jsou spojeny s projektem v dialogových oknech. Obsahuje jeden záznam na soubor nebo složku. Všechny soubory .vsdir v uváděného umístění jsou sloučeny, i když pouze jeden projektový soubor je obvykle zadáváno, k popisu více složek, průvodci nebo soubory šablon.  
  
 Složky (v podadresářích), soubory, které se odkazuje v projektový soubor a projektový soubor samotné jsou umístěny ve stejném adresáři. Když prostředí IDE spustí průvodce nebo zobrazuje složce nebo souboru v **nový projekt** nebo **přidat novou položku** dialogová okna, prostředí IDE prozkoumá adresář, který obsahuje spustit soubory, které chcete určit, zda je projektový soubor existuje. Pokud je nalezen projektový soubor, rozhraní IDE přečte ji k určení, zda obsahuje položku pro spuštění nebo zobrazené složky nebo souboru. Pokud se najde záznam, používá rozhraní IDE informace ve spuštění průvodce nebo zobrazení obsahu.  
  
 Následující příklad kódu je ze souboru SourceFiles.vsdir v \<EnvSDK > \BscPrj\BscPrj\BscPrjProjectItems\Source_Files klíč registru:  
  
```  
HeaderFile.h|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#125|130|#126|0|0|0|#127  
SourceFile.cpp|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#122|110|#123|0|0|0|#124  
```  
  
 V takovém případě jsou dva záznamy v jednom souboru. Nový řádek (návratový znak) odděluje jednotlivé záznamy. Každý řádek představuje jiný typ souboru. Svislicí (&#124;) odděluje pole v každém záznamu. Jeden adresář může obsahovat více .vsdir souborů, které mají názvy různých souborů, nebo může mít jeden projektový soubor pro každý typ souboru.  
  
## <a name="fields"></a>Pole  
 Následující tabulka uvádí pole určená pro každý záznam.  
  
|Pole|Popis|  
|-----------|-----------------|  
|Relativní cesta (RelPathName)|Název složky, šablonu nebo .vsz souboru, například HeaderFile.h nebo MyWizard.vsz. V tomto poli může být také název používá k reprezentování složku.|  
|{clsidPackage}|Identifikátor GUID VSPackage, který umožňuje přístup k lokalizovaných řetězců, jako je například LocalizedName, popis, IconResourceId a SuggestedBaseName, v VSPackage satelitní dynamická knihovna (DLL), prostředky. IconResourceId platí v případě, že není součástí DLLPath. **Poznámka:** toto pole je nepovinný, pokud jeden nebo více předchozích polí je identifikátor prostředku. Toto pole je obvykle prázdné, pokud .vsdir soubory, které odpovídají s použitím průvodců třetích stran, které nepřekládat jejich text.|  
|LocalizedName|Lokalizovaný název souboru šablony nebo průvodce. V tomto poli může být řetězec nebo identifikátor prostředku ve tvaru "#ResID". Tento název se zobrazí v **přidat novou položku** dialogové okno. **Poznámka:** Pokud LocalizedName je identifikátor prostředku, pak je vyžadován {clsidPackage}.|  
|SortPriority|Celé číslo představující relativní priorita tohoto souboru šablony nebo průvodce. Například pokud tato položka má hodnotu 1, pak tato položka se zobrazí vedle další položky s hodnotou 1 a před všechny položky s hodnotou řazení 2 nebo vyšší.<br /><br /> Priorita řazení je relativní vzhledem k položky ve stejném adresáři. Ve stejném adresáři může být více než jeden projektový soubor. V takovém případě položky ze všech *.* jsou sloučeny VSDIR soubory v tomto adresáři. Položky se stejnou prioritou jsou uvedeny v velká a malá písmena lexicographic pořadí zobrazovaný název. `_wcsicmp` Funkce slouží ke třídění položek.<br /><br /> Položky, které nejsou popsané v souborech .vsdir obsahovat číslo větší než číslo nejvyšší priority v souborech .vsdir priority. Výsledkem je, že jsou tyto položky na konci seznamu zobrazených bez ohledu na jejich název.|  
|Popis|Lokalizovaný popis průvodce nebo souboru šablony. V tomto poli může být řetězec nebo identifikátor prostředku ve tvaru "#ResID". Tento řetězec je zobrazen v **nový projekt** nebo **přidat novou položku** dialogové okno vybranou položku.|  
|DLLPath nebo {clsidPackage}|Umožňuje načíst ikonu pro průvodce nebo souboru šablony. Ikonu je pomocí IconResourceId načíst jako prostředek mimo souboru .dll nebo .exe. Tento soubor .dll nebo .exe lze identifikovat pomocí úplnou cestu nebo pomocí identifikátor GUID VSPackage. Implementace DLL VSPackage slouží k načtení ikonu (ne satelitní knihovny DLL).|  
|IconResourceId|Identifikátor prostředku DLL nebo VSPackage implementace knihovnu DLL, kterou určuje ikonu zobrazíte.|  
|Příznaky (<xref:Microsoft.VisualStudio.Shell.Interop.__VSDIRFLAGS>)|Umožňuje zakázat nebo povolit **název** a **umístění** polí na **přidat novou položku** dialogové okno. Hodnota **příznaky** pole je decimal ekvivalentem kombinace požadované bitové příznaky.<br /><br /> Když uživatel vybere položku na **nový** kartě projektu určuje, zda pole název a umístění pole se zobrazí při **přidat novou položku** se napřed zobrazí dialogové okno. Položku, prostřednictvím projektový soubor může řídit jenom jestli pole jsou povolené a zakázané vybranou položku.|  
|SuggestedBaseName|Představuje výchozí název souboru, průvodce nebo šablony. Toto pole je řetězec nebo identifikátor prostředku ve tvaru "#ResID". Rozhraní IDE používá tuto hodnotu jako výchozí název položky. Tato základní hodnota spolu s celočíselná hodnota má být název jedinečný, jako je například MyFile21.asp.<br /><br /> V předchozím seznamu popis, DLLPath, IconResourceId, příznaky a SuggestedBaseNumber platí pouze pro soubory šablony a průvodce. Tato pole se nevztahují ke složkám. Tato skutečnost ukazuje kód v souboru BscPrjProjectItems ve \<EnvSDK > \BscPrj\BscPrj\BscPrjProjectItems klíč registru. Tento soubor obsahuje tři záznamy (jeden pro každou složku) s čtyři pole pro každý záznam: RelPathName {clsidPackage} LocalizedName a SortPriority.<br /><br /> `General&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#110&#124;100`<br /><br /> `Source_Files&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#111&#124;110`<br /><br /> `Env&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#112&#124;120`|  
  
 Když vytvoříte soubor průvodce, měli byste také zvážit následující problémy.  
  
-   Každé pole bez potřeby, pro které neexistují smysluplný data by mělo obsahovat 0 (nula) jako zástupný znak.  
  
-   Pokud je zadaný žádný lokalizovaný název, název relativní cesty se používá v souboru průvodce.  
  
-   DLLPath přepíše clsidPackage pro umístění ikony.  
  
-   Pokud je definována žádná ikona, rozhraní IDE nahradí výchozí ikonu pro soubor, který má rozšíření.  
  
-   Pokud je zadaný žádný navrhované základní název, 'Project' se používá.  
  
-   Pokud odstraníte soubory .vsz, složek nebo souborů šablon, musíte odstranit jejich přidružené záznamy také z projektový soubor.  
  
## <a name="see-also"></a>Viz také  
 [Průvodci](../../extensibility/internals/wizards.md)   
 [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)