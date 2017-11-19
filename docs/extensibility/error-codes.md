---
title: "Kódy chyb | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error codes, source control plug-ins
- source control plug-ins, error codes
- errors [Visual Studio SDK]
ms.assetid: d9cbd1c4-719b-467a-8100-333c1e146d3b
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 50d05e529a3202f59df53801728b40fee1c68f40
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-codes"></a>Kódy chyb
Když zdroj ovládacího prvku Plug-in rozhraní API funkce vrátí chybu, očekává se, že se na jednu z následujících kódů chyb. Záporná, varování nebo informační chybové kódy jsou kladné, jsou všechny chyby a úspěchu je 0.  
  
|Kód chyby|Hodnota|Popis|  
|----------------|-----------|-----------------|  
|`SCC_I_SHARESUBPROJOK`|7|Modul plug-in podporuje přidávání souborů od správy zdrojového kódu ve dvou krocích. Další informace najdete v tématu [SccSetOption](../extensibility/sccsetoption-function.md).|  
|`SCC_I_FILEDIFFERS`|6|Místního souboru se liší od souboru v databázi pro správu zdrojů (například [SccDiff](../extensibility/sccdiff-function.md) může vrátit tuto hodnotu).|  
|`SCC_I_RELOADFILE`|5|Místní soubor byl změněn při operaci správy zdrojů; prostředí IDE má-li to možné znovu načíst soubor.|  
|`SCC_I_FILENOTAFFECTED`|4|Soubor nemá vliv.|  
|`SCC_I_PROJECTCREATED`|3|Vytvoření projektu při operaci správy zdrojů (například během volání [SccOpenProject](../extensibility/sccopenproject-function.md) při `SCC_OP_CREATEIFNEW` zadán příznak).|  
|`SCC_I_OPERATIONCANCELED`|2|Operace byla zrušena.|  
|`SCC_I_ADV_SUPPORT`|1|Modul plug-in podporuje rozšířené možnosti pro tento příkaz. Další informace najdete v tématu [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md).|  
|`SCC_OK`|0|Úspěch.|  
|`SCC_E_INITIALIZEFAILED`|-1|Chyba: Inicializace se nezdařila.|  
|`SCC_E_UNKNOWNPROJECT`|-2|Chyba: projektu neznámý.|  
|`SCC_E_COULDNOTCREATEPROJECT`|-3|Chyba: projektu se nezdařilo.|  
|`SCC_E_NOTCHECKEDOUT`|-4|Chyba: soubor není rezervována.|  
|`SCC_E_ALREADYCHECKEDOUT`|-5|Chyba: soubor je již rezervován.|  
|`SCC_E_FILEISLOCKED`|-6|Chyba: soubor je uzamčen.|  
|`SCC_E_FILEOUTEXCLUSIVE`|-7|Chyba: soubor je výhradně rezervována.|  
|`SCC_E_ACCESSFAILURE`|-8|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|`SCC_E_CHECKINCONFLICT`|-9|Chyba: při vrácení se změnami došlo ke konfliktu.|  
|`SCC_E_FILEALREADYEXISTS`|-10|Chyba: soubor již existuje.|  
|`SCC_E_FILENOTCONTROLLED`|-11|Chyba: soubor není ve správě zdrojového kódu.|  
|`SCC_E_FILEISCHECKEDOUT`|-12|Chyba: soubor je rezervován.|  
|`SCC_E_NOSPECIFIEDVERSION`|-13|Chyba: není žádná zadané verze.|  
|`SCC_E_OPNOTSUPPORTED`|-14|Chyba: operace není podporována.|  
|`SCC_E_NONSPECIFICERROR`|-15|Došlo k nespecifikované chybě.|  
|`SCC_E_OPNOTPERFORMED`|-16|Chyba, operace nebyla provedena.|  
|`SCC_E_TYPENOTSUPPORTED`|-17|Chyba: typ souboru, například binární, nepodporuje správu zdrojového kódu.|  
|`SCC_E_VERIFYMERGE`|-18|Soubor byl sloučit automaticky, ale nebyla vrácena vzhledem k tomu, že je ověření uživatele čekající na vyřízení.|  
|`SCC_E_FIXMERGE`|-19|Soubor byl sloučit automaticky, ale nebyla vrácena z důvodu konfliktu sloučení, který je třeba vyřešit ručně.|  
|`SCC_E_SHELLFAILURE`|-20|Došlo k chybě z důvodu chyby prostředí.|  
|`SCC_E_INVALIDUSER`|-21|Chyba: uživatel je neplatný.|  
|`SCC_E_PROJECTALREADYOPEN`|-22|Chyba: projekt je již otevřeno.|  
|`SCC_E_PROJSYNTAXERR`|-23|Chyba syntaxe projektu.|  
|`SCC_E_INVALIDFILEPATH`|-24|Chyba: cesta k souboru je neplatný.|  
|`SCC_E_PROJNOTOPEN`|-25|Chyba: projektu není otevřené.|  
|`SCC_E_NOTAUTHORIZED`|-26|Chyba: uživatel nemá oprávnění k provedení této operace.|  
|`SCC_E_FILESYNTAXERR`|-27|Chyba syntaxe souboru.|  
|`SCC_E_FILENOTEXIST`|-28|Chyba, místního souboru neexistuje.|  
|`SCC_E_CONNECTIONFAILURE`|-29|Chyba: došlo k chybě připojení.|  
|`SCC_E_UNKNOWNERROR`|-30|Došlo k neznámé chybě.|  
|`SCC_E_BACKGROUNDGETINPROGRESS`|-31|Aktuálně probíhá operace get pozadí.|  
  
## <a name="macros-provided-for-quick-checking"></a>Makra poskytuje rychlé kontroly  
  
```cpp  
IS_SCC_ERROR(rtn) (((rtn) < 0) ? TRUE : FALSE)  
IS_SCC_SUCCESS(rtn) (((rtn) == SCC_OK) ? TRUE : FALSE)  
IS_SCC_WARNING(rtn) (((rtn) > 0) ? TRUE : FALSE)  
```  
  
## <a name="remarks"></a>Poznámky  
 Všechny funkce rozhraní API modulu Plugin zdroj ovládací prvek (s výjimkou [SccAdd](../extensibility/sccadd-function.md), [SccCheckin](../extensibility/scccheckin-function.md), a [SccDiff](../extensibility/sccdiff-function.md)) se očekává, že úspěšná, pokud se místní soubory, které se předávají jako argumenty nejsou k dispozici v pracovní složku. Prostředí IDE může například vydávat volání [SccCheckout](../extensibility/scccheckout-function.md) nebo [SccUncheckout](../extensibility/sccuncheckout-function.md) na soubor, který neexistuje v pracovní složku, ale existuje v systému správy zdrojů. Toto volání bude úspěšné. Jenom v případě, že není dostupný žádný soubor ve složce práci nebo ve zdrojovém systému řízení funkce očekává se nezdaří.  
  
 Některé funkce, jako například `SccAdd` a `SccCheckin`, konkrétně by měla vrátit `SCC_E_FILENOTEXIST` při soubor ve složce pracovní neexistuje. Očekává se, že jiných funkcí úspěšně, pokud pracovní soubor neexistuje, pokud funkce fungovat na platný název souboru v systému správy zdrojů.  
  
 Modul plug-in správy zdroje měli žádné předpoklady týkající se oprávnění u souboru ve složce funkční i v případě, že modul plug-in měl označena jako soubor jen pro čtení během nějaké operace. Soubor ve složce pracovní můžete přesunout, odstranit a změnit mimo moduly v doplňku na ovládací prvek.  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)