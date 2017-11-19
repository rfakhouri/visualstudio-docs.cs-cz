---
title: "Bitové příznaky používané určité příkazy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, bitflags used by specific commands
ms.assetid: 37969977-6f7d-45c9-ba03-1306ae71f5d1
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e66d0f67e3774b1cbc908bb6b1bd13884a1d3171
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bitflags-used-by-specific-commands"></a>Bitové příznaky, které používá konkrétní příkazy
Chování počet funkcí v rozhraní API ovládacího prvku Plug-in zdroje můžete upravit nastavení jeden nebo více bitů jedinou hodnotu. Tyto hodnoty jsou označovány jako bitové příznaky. Různé bitové příznaky používá rozhraní API ovládacího prvku Plug-in zdroje jsou podrobně popsané tady seskupených podle funkce, která je používá.  
  
## <a name="checked-out-flag"></a>Rezervována příznak  
 Tento příznak se dá nastavit pro buď [SccAdd](../extensibility/sccadd-function.md) nebo [SccCheckin](../extensibility/scccheckin-function.md).  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`SCC_KEEP_CHECKEDOUT`|0x1000|Nechte soubor rezervovaný.|  
  
## <a name="add-flags"></a>Přidání příznaků  
 Tyto příznaky jsou používány [SccAdd](../extensibility/sccadd-function.md).  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`SCC_FILETYPE_AUTO`|0x00|Modul plug-in zdrojového kódu se očekává automaticky zjistí, zda je soubor textu nebo binárních.|  
|`SCC_FILETYPE_TEXT`|0x01|Typ souboru je text.|  
|`SCC_FILETYPE_BINARY`|0x04|Typ souboru není binární. **Poznámka:** `SCC_FILETYPE_TEXT` a `SCC_FILETYPE_BINARY` se vzájemně vylučují.   Nastavte právě jeden nebo ani jeden z nich.|  
|`SCC_ADD_STORELATEST`|0x02|Uložit pouze nejnovější verzi (žádné rozdíly).|  
  
## <a name="diff-flags"></a>Diff příznaky  
 [SccDiff](../extensibility/sccdiff-function.md) používá tyto příznaky k definování oboru rozdílové operace. `SCC_DIFF_QD_xxx` Se vzájemně vylučují. Pokud je zadána kterákoli z nich, visual zpětná vazba je má být poskytnut. V "rychlý rozdílové" (hloubka fronty), modul plug-in nezjišťuje, jak se liší, pouze pokud je jiný soubor. Pokud žádná z tyto příznaky je zadán, že se provádí "visual rozdílové"; podrobný soubor rozdíly jsou počítaný a zobrazí. Pokud požadovaný hloubka fronty není podporován, modul plug-in přesune na další stránku nejlepší. Například pokud IDE požadavků kontrolních součtů a modul plug-in nepodporuje, modul plug-in nemá full obsah zkontrolujte (stále mnohem rychleji než visual zobrazení).  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`SCC_DIFF_IGNORECASE`|0x0002|Ignorujte případu rozdíly.|  
|`SCC_DIFF_IGNORESPACE`|0x0004|Ignorujte rozdíly prázdný. **Poznámka:** `SCC_DIFF_IGNORECASE` a `SCC_DIFF_IGNORESPACE` příznaky jsou volitelné bitové příznaky.|  
|`SCC_DIFF_QD_CONTENTS`|0x0010|Hloubka fronty srovnáním celý soubor obsahu.|  
|`SCC_DIFF_QD_CHECKSUM`|0x0020|Hloubka fronty podle kontrolního součtu.|  
|`SCC_DIFF_QD_TIME`|0x0040|Hloubka fronty pomocí razítka data a času souboru.|  
|`SCC_DIFF_QUICK_DIFF`|0x0070|Toto je masku použita ke kontrole všechny bitové příznaky hloubka fronty. By neměly být předány do funkce; tři bitové příznaky hloubka fronty se vzájemně vylučují. Hloubka fronty vždy znamená bez zobrazení uživatelského rozhraní.|  
  
## <a name="populatelist-flag"></a>Příznak PopulateList  
 Tento příznak se používá [SccPopulateList](../extensibility/sccpopulatelist-function.md) v `fOptions` parametr.  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`SCC_PL_DIR`|0x00000001L|Prostředí IDE dojde k předání adresáře, ne soubory.|  
  
## <a name="populatedirlist-flags"></a>Příznaky PopulateDirList  
 Tyto příznaky jsou používány [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) v `fOptions` parametr.  
  
|Hodnota možnosti|Hodnota|Popis|  
|------------------|-----------|-----------------|  
|SCC_PDL_ONELEVEL|0x0000|Zkontrolujte pouze jedna úroveň adresářů pro adresáře (to je výchozí hodnota).|  
|SCC_PDL_RECURSIVE|0x0001|Rekurzivní zkontrolujte všechny adresáře na každý daný adresář.|  
|SCC_PDL_INCLUDEFILES|0x0002|Zahrňte do procesu prozkoumání názvy souborů.|  
  
## <a name="openproject-flags"></a>Příznaky OpenProject  
 Tyto příznaky jsou používány [SccOpenProject](../extensibility/sccopenproject-function.md) v `dwFlags` parametr.  
  
|Hodnota možnosti|Hodnota|Popis|  
|------------------|-----------|-----------------|  
|SCC_OP_CREATEIFNEW|0x00000001L|Pokud projekt neexistuje ve správě zdrojového kódu, vytvořte ho. Pokud není nastavený tento příznak, zobrazit výzvu uživateli pro projekt pro vytvoření (Pokud `SCC_OP_SILENTOPEN` zadán příznak).|  
|SCC_OP_SILENTOPEN|0x00000002L|Nezobrazovat výzvu k vytvoření projektu; vrácena `SCC_E_UNKNOWNPROJECT`.|  
  
## <a name="get-flags"></a>Získat příznaky  
 Tyto příznaky jsou používány [SccGet](../extensibility/sccget-function.md) a [SccCheckout](../extensibility/scccheckout-function.md).  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`SCC_GET_ALL`|0x00000001L|Prostředí IDE je předávání adresáře, není soubory: získat všechny soubory v těchto adresářů.|  
|`SCC_GET_RECURSIVE`|0x00000002L|Prostředí IDE je předávání adresáře: získat tyto adresáře a všech jejich podadresářů.|  
  
## <a name="noption-values"></a>nOption hodnoty  
 Tyto příznaky jsou používány [SccSetOption](../extensibility/sccsetoption-function.md) v `nOption` parametr.  
  
|Příznak|Hodnota|Popis|  
|----------|-----------|-----------------|  
|`SCC_OPT_EVENTQUEUE`|0x00000001L|Nastavte stav fronty událostí.|  
|`SCC_OPT_USERDATA`|0x00000002L|Zadejte uživatelská data pro `SCC_OPT_NAMECHANGEPFN`.|  
|`SCC_OPT_HASCANCELMODE`|0x00000003L|Prostředí IDE dokáže zpracovat Storno|  
|`SCC_OPT_NAMECHANGEPFN`|0x00000004L|Nastaví zpětné volání pro změny názvu.|  
|`SCC_OPT_SCCCHECKOUTONLY`|0x00000005L|Zakažte zdroj ovládacího prvku modulu plug-in uživatelského rozhraní checkout a nenastavujte pracovní adresář.|  
|`SCC_OPT_SHARESUBPROJ`|0x00000006L|Přidejte ze správy zdrojového kódu zadat pracovní adresář. Můžete se pokuste sdílet do přidružených projektu, pokud je přímý následníka.|  
  
## <a name="dwval-bitflags"></a>dwVal bitové příznaky  
 Tyto příznaky jsou používány [SccSetOption](../extensibility/sccsetoption-function.md) v `dwVal` parametr.  
  
|Příznak|Hodnota|Popis|Používá `nOption` hodnota|  
|----------|-----------|-----------------|-----------------------------|  
|`SCC_OPT_EQ_DISABLE`|0x00L|Pozastaví aktivity fronty události.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_EQ_ENABLE`|0x01L|Povolí protokolování událostí fronty.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_HCM_NO`|0L|(Výchozí) Nemá žádný režim zrušit; modul plug-in musí zadat v případě potřeby.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_HCM_YES`|1L|IDE zpracovává Storno.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_SCO_NO`|0L|(Výchozí) OK rezervovat z modulu plug-in uživatelského rozhraní; pracovní adresář je nastaven.|`SCC_OPT_SCCCHECKOUTONLY`|  
|`SCC_OPT_SCO_YES`|1L|Žádné modulu plug-in checkout uživatelského rozhraní, žádné pracovní adresář.|`SCC_OPT_SCCCHECKOUTONLY`|  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)