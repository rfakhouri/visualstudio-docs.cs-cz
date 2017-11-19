---
title: Funkce SccGetParentProjectPath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetParentProjectPath
helpviewer_keywords: SccGetParentProjectPath function
ms.assetid: 62a71579-36b3-48b9-a1c8-04ab100efa08
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 47cf6ee34738e8830705c0bed30891223efcd103
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sccgetparentprojectpath-function"></a>SccGetParentProjectPath – funkce
Tato funkce určuje nadřazená cesta projektu zadaného projektu. Tato funkce je volána, když uživatel je přidání projektu sady Visual Studio k řízení zdrojů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGetParentProjectPath(  
   LPVOID pContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPCSTR lpProjPath,  
   LPSTR  lpAuxProjPath,  
   LPSTR  lpParentProjPath  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Ukazatel modulu plug-in kontextu zdroj ovládacího prvku.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpUser  
 [ve out] Uživatelské jméno (až SCC_USER_SIZE, včetně ukončení NULL).  
  
 lpProjPath  
 [v] Řetězec identifikující cesta k projektu (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 lpAuxProjPath  
 [ve out] Pomocná řetězec identifikující projektu (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 lpParentProjPath  
 [ve out] Výstupní řetězec identifikující nadřazená cesta projektu (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Nadřazená cesta projektu byl byly úspěšně načteny.|  
|SCC_E_INITIALIZEFAILED|Projekt nelze inicializovat.|  
|SCC_E_INVALIDUSER|Uživatel se nemohla přihlásit modulu plug-in zdrojového kódu.|  
|SCC_E_UNKNOWNPROJECT|Projekt Neznámý k řízení zdrojů, modul plug-in.|  
|SCC_E_INVALIDFILEPATH|Cesta k souboru neplatný nebo není použitelná.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_PROJSYNTAXERR|Syntaxe projektu není platné.|  
|SCC_E_CONNECTIONFAILURE|Potíže s připojením úložiště.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce vrátí hodnotu úspěch nebo neúspěch a v případě úspěchu se doplní proměnnou `lpParentProjPath` s cestou úplné projektu do zadaného projektu.  
  
 Tato funkce vrátí nadřazené cesty k projektu existujícího projektu. Pro kořenový projekt, vrátí funkce cesta k projektu, který byl předán v (tedy stejné kořenové projektu cesta). Všimněte si, že cesta projektu řetězec, který má smysl pouze na modul plug-in zdrojového kódu.  
  
 Prostředí IDE je připraven přijmout změny `lpUser` a `lpAuxProjPath` také parametry. Prostředí IDE se zachovat tyto řetězce a předat je do [SccOpenProject](../extensibility/sccopenproject-function.md) když uživatel otevře tohoto projektu v budoucnu. Tyto řetězce, tedy poskytují způsob pro modul plug-in pro sledování informace, které je potřeba přidružit projektu zdrojového kódu.  
  
 Tato funkce je podobná [SccGetProjPath](../extensibility/sccgetprojpath-function.md)kromě toho, že se nezobrazí výzvu uživateli vybrat projektu. Také nikdy vytvoří nový projekt, ale funguje jenom s existujícího projektu.  
  
 Když `SccGetParentProjectPath` je volána, `lpProjPath` a `lpAuxProjPath` nesmí být prázdný a bude odpovídat na platný projekt. Tyto řetězce jsou obvykle přijímány IDE z předchozího volání `SccGetProjPath` funkce.  
  
 `lpUser` Argument je uživatelské jméno. Prostředí IDE předá ve stejné uživatelské jméno, který byl dříve získali od `SccGetProjPath` funkce a modul plug-in zdrojového kódu má použít jako výchozí název. Pokud uživatel už má otevřené připojení s modulem plug-in, modul plug-in musí opakujte omezit zobrazování výzev a ujistěte se, že funkce funguje bez upozornění. Ale pokud přihlášení selže, modul plug-in by se zobrazit výzva uživatele pro přihlášení, když obdrží platného přihlášení, předejte název zpět na `lpUser`. Protože modul plug-in může změnit tento řetězec, rozhraní IDE vždy přidělit vyrovnávací paměť o velikosti (`SCC_USER_LEN`+ 1). Pokud řetězec změnil, nový řetězec musí být platným přihlašovacím jménem (alespoň jako platná jako původní řetězec).  
  
## <a name="technical-notes-for-scccreatesubproject-and-sccgetparentprojectpath"></a>Technické poznámky pro SccCreateSubProject a SccGetParentProjectPath  
 Přidání řešení a projekty do správy zdrojového kódu je jednodušší v sadě Visual Studio, chcete-li minimalizovat počet, který je uživatel vyzván k výběru umístění v systému správy zdrojů. Tyto změny jsou aktivované pomocí sady Visual Studio, pokud modul plug-in správy zdroje podporuje i nové funkce [SccCreateSubProject](../extensibility/scccreatesubproject-function.md) a `SccGetParentProjectPath` funkce. Následující položky registru však lze zakázat tyto změny a obnovit předchozí chování sady Visual Studio (Zdroj ovládacího prvku Plug-in rozhraní API verze 1.1):  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
 Pokud tato položka registru neexistuje nebo je nastaven na DWORD: 00000000, Visual Studio se pokusí použít nové funkce, `SccCreateSubProject`a`SccGetParentProjectPath`.  
  
 Pokud je položka registru nastavena na DWORD: 00000001, Visual Studio nebude pokoušet použít tyto nové funkce a operace přidání do správy zdrojového kódu fungují stejně jako v předchozích verzích sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccCreateSubProject](../extensibility/scccreatesubproject-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)