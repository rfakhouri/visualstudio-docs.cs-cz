---
title: Funkce SccSetOption | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccSetOption
helpviewer_keywords: SccSetOption function
ms.assetid: 4b5e6666-c24c-438a-a9df-9c52f58f8175
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 70fe624984adce58191ee7d354185eac0bb527ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccsetoption-function"></a>SccSetOption – funkce
Tato funkce se nastaví možnosti, které řídí chování modulu plug-in zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccSetOption(  
   LPVOID pvContext,  
   LONG   nOption,  
   LONG   dwVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 nOption  
 [v] Možnost, která je nastavena.  
  
 dwVal  
 [v] Nastavení pro možnost.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Možnost byl úspěšně nastaven.|  
|SCC_I_SHARESUBPROJOK|Vrácené v případě `nOption` byla `SCC_OPT_SHARESUBPROJ` a modul plug-in zdrojového kódu umožňuje IDE nastavit cílovou složku.|  
|SCC_E_OPNOTSUPPORTED|Možnost nebyla nastavena a nemělo by být spoléhat.|  
  
## <a name="remarks"></a>Poznámky  
 Prostředí IDE volání této funkce můžete řídit chování modulu plug-in zdrojového kódu. První parametr `nOption`, označuje hodnotu, která je nastavena, zatímco druhý, `dwVal`, určuje, co dělat s touto hodnotou. Modul plug-in ukládá tyto informace související s `pvContext``,` tak IDE musí volat tuto funkci po volání [SccInitialize](../extensibility/sccinitialize-function.md) (ale nemusí po každé volání [SccOpenProject](../extensibility/sccopenproject-function.md)).  
  
 Přehled možností a jejich hodnoty:  
  
|`nOption`|`dwValue`|Popis|  
|---------------|---------------|-----------------|  
|`SCC_OPT_EVENTQUEUE`|`SCC_OPT_EQ_DISABLE`<br /><br /> `SCC_OPT_EQ_ENABLE`|Povolí nebo zakáže na pozadí služby Řízení front událostí.|  
|`SCC_OPT_USERDATA`|Libovolná hodnota|Určuje hodnotu uživatele mají být předány [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) funkce zpětného volání.|  
|`SCC_OPT_HASCANCELMODE`|`SCC_OPT_HCM_NO`<br /><br /> `SCC_OPT_HCM_YES`|Určuje, zda IDE aktuálně podporuje, zrušení operace.|  
|`SCC_OPT_NAMECHANGEPFN`|Ukazatel [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) funkce zpětného volání|Nastaví ukazatel na funkci zpětného volání Změna názvu.|  
|`SCC_OPT_SCCCHECKOUTONLY`|`SCC_OPT_SCO_NO`<br /><br /> `SCC_OPT_SCO_YES`|Určuje, zda rozhraní IDE umožňuje kontrolu mimo jeho soubory ručně (pomocí uživatelského rozhraní pro řízení zdrojového) nebo jestli se musí být rezervována pouze pomocí modulu plug-in zdrojového kódu.|  
|`SCC_OPT_SHARESUBPROJ`|Není k dispozici|Pokud modul plug-in zdrojového kódu umožňuje IDE zadat složku, místní projektu, modul plug-in vrátí `SCC_I_SHARESUBPROJOK`.|  
  
## <a name="sccopteventqueue"></a>SCC_OPT_EVENTQUEUE  
 Pokud `nOption` je `SCC_OPT_EVENTQUEUE`, rozhraní IDE zakázání (nebo opětovné povolení) zpracování na pozadí. Během kompilace, například rozhraní IDE může vyzvat modulu plug-in zastavit zpracování při nečinnosti libovolného typu zdrojového kódu. Po kompilace ho by znovu povolit zpracování na pozadí aktualizovat moduly v doplňku na fronty událostí. Odpovídající `SCC_OPT_EVENTQUEUE` hodnotu `nOption`, existují dvě možné hodnoty pro `dwVal`, konkrétně, `SCC_OPT_EQ_ENABLE` a `SCC_OPT_EQ_DISABLE`.  
  
## <a name="sccopthascancelmode"></a>SCC_OPT_HASCANCELMODE  
 Pokud hodnota `nOption` je `SCC_OPT_HASCANCELMODE`, rozhraní IDE umožňuje uživatelům zrušit dlouhá operace. Nastavení `dwVal` k `SCC_OPT_HCM_NO` (výchozí) znamená, že rozhraní IDE má žádný režim Storno. Správa zdrojového kódu modul plug-in musí nabízejí vlastní tlačítko Zrušit, pokud chce uživatel moct zrušit. `SCC_OPT_HCM_YES`Označuje, že rozhraní IDE poskytuje schopnost zrušte operace, takže není nutné zobrazit svou vlastní tlačítko Zrušit SCC modulu plug-in. Pokud je nastaví prostředí IDE `dwVal` k `SCC_OPT_HCM_YES`, je připraveno reagovat na `SCC_MSG_STATUS` a `DOCANCEL` zprávy odeslané do `lpTextOutProc` funkce zpětného volání (najdete v části [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)). Pokud IDE Tato proměnná nenastaví, by neměl modul plug-in odeslat těchto dvou zprávách.  
  
## <a name="sccoptnamechangepfn"></a>SCC_OPT_NAMECHANGEPFN  
 Pokud nOption je nastaven na `SCC_OPT_NAMECHANGEPFN`a jak zdroj modul plug-in správy a rozhraní IDE povolit, modul plug-in můžete ve skutečnosti přejmenovat nebo přesunout do souboru během operace řízení zdroje. `dwVal` Bude nastavena pro ukazatel na funkci typu [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md). Během operace řízení zdroje modul plug-in můžete volat tuto funkci předávání v tři parametry. Jedná se o starý název (s plně kvalifikovanou cestu) souboru, nový název (s plně kvalifikovanou cestu) souboru a odkaz na informace, která má vztah k rozhraní IDE. Prostředí IDE odešle v tento poslední ukazatel voláním `SccSetOption` s `nOption` nastavena na `SCC_OPT_USERDATA`, s `dwVal` odkazující na data. Podpora pro tuto funkci je volitelné. VSSCI plug-, používá tato schopnost musí inicializovat jeho funkce ukazatel a uživatel datových proměnných na `NULL`, a pokud ji nebyla zadána jedna ho nesmí volání funkce přejmenování. Je také je třeba připravit pro uložení byla zadána hodnota, nebo ho můžete změnit v reakci na nové volání na `SccSetOption`. Tím nedojde k ní uprostřed operaci příkaz správy zdrojů, ale k tomu může dojít mezi příkazy.  
  
## <a name="sccoptscccheckoutonly"></a>SCC_OPT_SCCCHECKOUTONLY  
 Pokud nOption je nastaven na `SCC_OPT_SCCCHECKOUTONLY`, rozhraní IDE oznamuje, že soubory v aktuálně otevřených projekt by nikdy rezervovat ručně prostřednictvím uživatelského rozhraní systému správy zdrojů. Místo toho by měla být rezervována soubory pouze pomocí modulu plug-in pod kontrolou IDE zdrojového kódu. Pokud `dwValue` je nastaven na `SCC_OPT_SCO_NO`, ho znamená, že soubory by se normálně zpracovávat pomocí modulu plug-in a rezervací prostřednictvím zdrojového kódu uživatelského rozhraní. Pokud `dwValue` je nastaven na `SCC_OPT_SCO_YES`, pak pouze modul plug-in je povoleno se soubory a uživatelské rozhraní systému správy zdrojů by neměla být volána. Toto je pro situace, kde integrovaného vývojového prostředí může mít "pseudo soubory", které dávají smysl rezervovat pouze prostřednictvím prostředí IDE.  
  
## <a name="sccoptsharesubproj"></a>SCC_OPT_SHARESUBPROJ  
 Pokud`nOption` je nastaven na `SCC_OPT_SHARESUBPROJ`, rozhraní IDE je testování, zda modul plug-in zdrojového kódu můžete použít místní složky zadané při přidávání souborů od správy zdrojového kódu. Hodnota `dwVal` parametr v tomto případě nezáleží. Pokud modul plug-in umožňuje IDE zadat místní cílovou složku, kam bude přidána soubory ze zdroje řídit, kdy [SccAddFromScc](../extensibility/sccaddfromscc-function.md) je volána, pak musí vracet modul plug-in `SCC_I_SHARESUBPROJOK` při `SccSetOption` je funkce volá se. Prostředí IDE použije `lplpFileNames` parametr `SccAddFromScc` funkce předávání v cílové složce. Modul plug-in používá tuto cílovou složku pro soubory přidat od správy zdrojového kódu. Pokud modul plug-in nevrátí `SCC_I_SHARESUBPROJOK` při `SCC_OPT_SHARESUBPROJ` je možnost nastavena, rozhraní IDE předpokládá, že modul plug-in je možné přidat soubory pouze v místním adresáři aktuální.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccAddFromScc](../extensibility/sccaddfromscc-function.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)   
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)