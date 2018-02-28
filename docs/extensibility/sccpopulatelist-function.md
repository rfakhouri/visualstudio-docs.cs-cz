---
title: Funkce SccPopulateList | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccPopulateList
helpviewer_keywords:
- SccPopulateList function
ms.assetid: 7416e781-c571-4a7f-8af3-a089ce8be662
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 474bb834d36661c7cd85b98db78c13f619d7cba6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccpopulatelist-function"></a>SccPopulateList – funkce
Tato funkce aktualizuje seznam souborů pro příkaz konkrétní zdroj ovládacího prvku a poskytuje stav zdroje ovládacího prvku na všechny dané soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccPopulateList (  
   LPVOID          pvContext,  
   enum SCCCOMMAND nCommand,  
   LONG            nFiles,  
   LPCSTR*         lpFileNames,  
   POPLISTFUNC     pfnPopulate,  
   LPVOID          pvCallerData,  
   LPLONG          lpStatus,  
   LONG            fOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 Npříkaz  
 [v] Příkaz řízení zdroje, které se použijí na všechny soubory v `lpFileNames` pole (najdete v části [příkaz kódu](../extensibility/command-code-enumerator.md) pro seznam možných příkazů).  
  
 : %{nfiles/  
 [v] Počet souborů v `lpFileNames` pole.  
  
 lpFileNames  
 [v] Pole názvy souborů ví, že rozhraní IDE.  
  
 pfnPopulate  
 [v] Funkce zpětného volání IDE volání přidávat a odebírat soubory (viz [POPLISTFUNC](../extensibility/poplistfunc.md) podrobnosti).  
  
 pvCallerData  
 [v] Hodnota, která má být předán beze změny funkce zpětného volání.  
  
 lpStatus  
 [ve out] Pole pro modul plug-in vrátit příznaky stavu pro každý soubor zdrojového kódu.  
  
 fOptions  
 [v] Příkaz příznaky (naleznete v části "PopulateList příznak" [bitové příznaky používané určité příkazy](../extensibility/bitflags-used-by-specific-commands.md) podrobnosti).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěch.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce prověří seznam souborů pro jeho aktuální stav. Použije `pfnPopulate` funkce zpětného volání, které oznámí souboru neodpovídá kritériím pro volající `nCommand`. Například, pokud je příkaz `SCC_COMMAND_CHECKIN` a není rezervována souborů v seznamu, pak zpětné volání slouží k informování volající. Modul plug-in zdrojového kódu v některých případech může najít další soubory, které může být součástí příkazu a přidat je. To umožňuje například uživateli jazyka Visual Basic .bmp soubor, který je používán své projektu, ale nejsou uvedené v souboru projektu jazyka Visual Basic. Uživatel rozhodne **získat** příkazu v prostředí IDE. Prostředí IDE zobrazí seznam všech souborů, které se domnívá, že uživatel můžete získat, ale předtím, než se zobrazí v seznamu, `SccPopulateList` funkce je volána, abyste měli jistotu, který se má zobrazit v seznamu je aktuální.  
  
## <a name="example"></a>Příklad  
 Prostředí IDE sestavuje seznam souborů, které se domnívá, že uživatel může získat. Předtím, než se zobrazí tento seznam, zavolá `SccPopulateList` fungovat, poskytuje modul plug-in Zdroj kontrolu možnost Přidat a odstranit soubory ze seznamu. Modul plug-in upraví voláním funkce zpětného volání daného seznamu (viz [POPLISTFUNC](../extensibility/poplistfunc.md) další podrobnosti).  
  
 Modul plug-in nadále volání `pfnPopulate` funkci, která přidá a odstraní soubory, dokud ji po dokončení a vrátí z `SccPopulateList` funkce. Prostředí IDE pak můžete zobrazit jeho seznamu. `lpStatus` Pole představuje všechny soubory v seznamu původní předaná v prostředí IDE. Modul plug-in vyplní stav všechny tyto soubory kromě provádění pomocí funkce zpětného volání.  
  
> [!NOTE]
>  Správa zdrojového kódu modulu plug-in má vždy možnost jednoduše okamžitě vrátit z této funkce a v seznamu, protože se jedná. Pokud modul plug-in implementuje tuto funkci, mohlo to znamenat nastavením `SCC_CAP_POPULATELIST` bitových parametrů funkce v prvním volání [SccInitialize](../extensibility/sccinitialize-function.md). Ve výchozím nastavení modul plug-in musí vždy předpokládají, že všechny položky, které jsou předávány v jsou soubory. Ale pokud je nastaví prostředí IDE `SCC_PL_DIR` příznak v `fOptions` parametr všechny položky, které jsou předávány v jsou považovány adresáře. Modul plug-in seznam by měl přidejte všechny soubory, které patří do adresáře. Prostředí IDE, projdou nikdy v kombinaci souborů a adresářů.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)   
 [Bitové příznaky, které používá konkrétní příkazy](../extensibility/bitflags-used-by-specific-commands.md)   
 [Příkaz kódu](../extensibility/command-code-enumerator.md)