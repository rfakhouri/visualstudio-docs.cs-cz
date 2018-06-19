---
title: Funkce SccOpenProject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccOpenProject
helpviewer_keywords:
- SccOpenProject function
ms.assetid: d609510b-660a-46d7-b93d-2406df20434d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 15d9cf6d5fa4533b5ee0ff65f8aeae86df3d571a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143371"
---
# <a name="sccopenproject-function"></a>SccOpenProject – funkce
Tato funkce otevře existující projekt řízení zdroje nebo vytvoří nový.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccOpenProject (  
   LPVOID        pvContext,  
   HWND          hWnd,  
   LPSTR         lpUser,  
   LPCSTR        lpProjName,  
   LPCSTR        lpLocalProjPath,  
   LPSTR         lpAuxProjPath,  
   LPCSTR        lpComment,  
   LPTEXTOUTPROC lpTextOutProc,  
   LONG          dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpUser  
 [ve out] Název uživatele (nesmí přesáhnout SCC_USER_SIZE, včetně ukončení NULL).  
  
 lpProjName  
 [v] Řetězec identifikující název projektu.  
  
 lpLocalProjPath  
 [v] Cesta k pracovní složku pro projekt.  
  
 lpAuxProjPath  
 [ve out] Volitelné pomocného řetězec identifikující projektu (nesmí přesáhnout SCC_AUXPATH_SIZE, včetně ukončení NULL).  
  
 lpComment  
 [v] Komentář na nový projekt, který je právě vytvářena.  
  
 lpTextOutProc  
 [v] Volitelné zpětného volání funkce zobrazení textu výstup z modulu plug-in zdrojového kódu.  
  
 dwFlags  
 [v] Signály zda nový projekt musí být vytvořen, pokud projekt není znám ke zdroji řídit modulu plug-in. Hodnota může být kombinací `SCC_OP_CREATEIFNEW` a `SCC_OP_SILENTOPEN.`  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěch v otevírání projektu.|  
|SCC_E_INITIALIZEFAILED|Projekt nelze inicializovat.|  
|SCC_E_INVALIDUSER|Uživatel se nemohla přihlásit do správy zdrojového kódu.|  
|SCC_E_COULDNOTCREATEPROJECT|Projekt neexistuje před volání;  `SCC_OPT_CREATEIFNEW` byl nastaven příznak, ale nebylo možné vytvořit projekt.|  
|SCC_E_PROJSYNTAXERR|Syntaxe projektu není platné.|  
|SCC_E_UNKNOWNPROJECT|Projekt Neznámý k řízení zdrojů, modul plug-in a `SCC_OPT_CREATEIFNEW` nebyl nastaven příznak.|  
|SCC_E_INVALIDFILEPATH|Cesta k souboru neplatný nebo není použitelná.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECFICERROR|K nespecifikované chybě; správy zdrojového kódu se neinicializoval.|  
  
## <a name="remarks"></a>Poznámky  
 Uživatelské jméno může předat rozhraní IDE (`lpUser`), nebo ho může jednoduše předat ukazatel na prázdný řetězec. Pokud je uživatelské jméno, modul plug-in zdrojového kódu má použít jako výchozí. Ale pokud nebyl předán žádný název, nebo pokud se přihlášení nezdařilo se zadaným názvem, modul plug-in by se zobrazit výzva k přihlášení uživatele a vrátí platný název v `lpUser` při přijetí platného přihlášení`.` vzhledem k tomu, že modul plug-in může změnit řetězec názvu uživatele , rozhraní IDE bude vždy přidělit vyrovnávací paměť o velikosti (`SCC_USER_LEN`+ 1 nebo SCC_USER_SIZE, včetně místa pro ukončení null).  
  
> [!NOTE]
>  Je první akcí integrovaného vývojového prostředí může být nutné provést může být volání `SccOpenProject` funkce nebo [SccGetProjPath](../extensibility/sccgetprojpath-function.md). Z tohoto důvodu mít oba dva identická `lpUser` parametr.  
  
 `lpAuxProjPath` a`lpProjName` jsou čtení ze souboru řešení, nebo jsou vráceny z volání `SccGetProjPath` funkce. Tyto parametry obsahují řetězce, které modul plug-in správy zdroje přidruží projektu a mají smysl jenom pro modul plug-in. Pokud žádná taková řetězce v souboru řešení a uživatel nebyl byl vyzván, aby Procházet (což by vrátit řetězec prostřednictvím `SccGetProjPath` funkce), rozhraní IDE předá prázdné řetězce pro obě `lpAuxProjPath` a `lpProjName`a předpokládá, že tyto hodnoty aktualizovat pomocí modulu plug-in když funkce vrátí hodnotu.  
  
 `lpTextOutProc` je zde ukazatel na funkci zpětného volání poskytované IDE pro modul plug-in pro účely zobrazení výstupu výsledek příkazu zdrojového kódu. Tato funkce zpětného volání je podrobně popsaná v [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
> [!NOTE]
>  Pokud modul plug-in zdrojového kódu se chtít využít výhody tohoto, musí mít nastavený `SCC_CAP_TEXTOUT` příznak v [SccInitialize](../extensibility/sccinitialize-function.md). Pokud nebyl nastaven tento příznak, nebo pokud rozhraní IDE nepodporuje tuto funkci `lpTextOutProc` bude `NULL`.  
  
 `dwFlags` Parametr řídí výsledek v případě, že otevíráte projekt neexistuje. Skládá se ze dvou bitové příznaky, `SCC_OP_CREATEIFNEW` a `SCC_OP_SILENTOPEN`. Pokud projekt otevíráte již existuje, funkce jednoduše otevře projektu a vrátí `SCC_OK`. Pokud projekt neexistuje a pokud `SCC_OP_CREATEIFNEW` příznak zapnutý, modul plug-in zdrojového kódu vytvoření projektu v systému správy zdrojů, otevřete ho a vrátí `SCC_OK`. Pokud projekt neexistuje a pokud `SCC_OP_CREATEIFNEW` příznak je vypnutý, modul plug-in by měla pak vyhledat `SCC_OP_SILENTOPEN` příznak. Pokud na tento příznak není, může modul plug-in vyzvat uživatele k zadání názvu projektu. Pokud je tento příznak na, modul plug-in jednoduše vrátit `SCC_E_UNKNOWNPROJECT`.  
  
## <a name="calling-order"></a>Pořadí volání  
 Při běžném průběhu, události [SccInitialize](../extensibility/sccinitialize-function.md) by nejprve zavolat otevřete relaci řízení zdroje. Relace se může skládat z volání `SccOpenProject`, za nímž následuje další volání funkcí API Plug-in Zdroj ovládacího prvku a bude ukončen pomocí volání [SccCloseProject](../extensibility/scccloseproject-function.md). Tyto relace mohou být opakovány několikrát před [SccUninitialize](../extensibility/sccuninitialize-function.md) je volána.  
  
 Pokud zdroj řízení modulu plug-in sady `SCC_CAP_REENTRANT` bit v `SccInitialize`, pak výše pořadí relace může opakuje tolikrát, kolikrát paralelně. Různé `pvContext` struktury sledovat různé relace, kde každá `pvContext` je přidružen jeden otevřete projekt v čase. Na základě`pvContext` parametr, modul plug-in můžete určit, který projekt se odkazuje v žádném volání, konkrétní. Pokud bit možnost `SCC_CAP_REENTRANT` není nastavena, nonreentrant zdroj ovládacího prvku zásuvné moduly mají omezenou schopnost pracovat s více projektů.  
  
> [!NOTE]
>  `SCC_CAP_REENTRANT` Bit byla zavedena v verze 1.1 rozhraní API ovládacího prvku Plug-in zdroje. Není nastaveno, nebo je ignorován v verze 1.0, a všechny verze 1.0 Zdroj ovládacího prvku moduly plug-in jsou považovány za nonreentrant.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCloseProject](../extensibility/scccloseproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [Omezení délky řetězce](../extensibility/restrictions-on-string-lengths.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)