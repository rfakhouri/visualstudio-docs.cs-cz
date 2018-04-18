---
title: Funkce SccCreateSubProject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccCreateSubProject
helpviewer_keywords:
- SccCreateSubProject function
ms.assetid: 08154aed-ae5c-463c-8694-745d0e332965
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fa87be4c9d22aca46814e8fa284fda9d587386a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="scccreatesubproject-function"></a>SccCreateSubProject – funkce
Tato funkce vytvoří dílčí projekt s daným názvem. v části existujícího projektu nadřazené určeného `lpParentProjPath` argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccCreateSubProject(  
   LPVOID pContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPCSTR lpParentProjPath,  
   LPCSTR lpSubProjName,  
   LPSTR  lpAuxProjPath,  
   LPSTR  lpSubProjPath  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Ukazatel modulu plug-in kontextu zdroj ovládacího prvku.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpUser  
 [ve out] Uživatelské jméno (až SCC_USER_SIZE, včetně ukončení NULL).  
  
 lpParentProjPath  
 [v] Řetězec, který určuje cestu nadřazený projekt (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 lpSubProjName  
 [v] Název dílčí navrhované projekt (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 lpAuxProjPath  
 [ve out] Pomocná řetězec identifikující projektu (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 lpSubProjPath  
 [ve out] Výstupní řetězec identifikující cesta k dílčí projekt (až SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dílčí projekt byl úspěšně vytvořen.|  
|SCC_E_INITIALIZEFAILED|Nepodařilo se inicializovat nadřazený projekt.|  
|SCC_E_INVALIDUSER|Uživatel se nemohla přihlásit do správy zdrojového kódu.|  
|SCC_E_COULDNOTCREATEPROJECT|Dílčí projekt nelze vytvořit.|  
|SCC_E_PROJSYNTAXERR|Syntaxe projektu není platné.|  
|SCC_E_UNKNOWNPROJECT|Nadřazený projekt Neznámý k řízení zdrojů, modul plug-in.|  
|SCC_E_INVALIDFILEPATH|Cesta k souboru neplatný nebo není použitelná.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_CONNECTIONFAILURE|Došlo k potížím zdroj ovládacího prvku modulu plug-in připojení.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud dílčí projekt s názvem již existuje, funkce můžete změnit výchozí název, chcete-li vytvořit jedinečný, například přidáním "_\<číslo >" k němu. Volající musí být připravené informace o přijetí změn na `lpUser`, `lpSubProjPath`, a `lpAuxProjPath`. `lpSubProjPath` a`lpAuxProjPath` argumenty jsou potom použít v volání [SccOpenProject](../extensibility/sccopenproject-function.md). By neměl být upraven volající po návratu. Tyto řetězce poskytují způsob pro modul plug-in pro sledování informací, které je potřeba přidružit projektu zdrojového kódu. Volající IDE nezobrazí tyto dva parametry po návratu, protože modul plug-in můžete použít formátovaný řetězec, který nemusí být vhodný pro zobrazení. Funkce vrátí hodnotu úspěch nebo neúspěch a v případě úspěchu se doplní proměnnou `lpSubProjPath` s cestou úplné projektu do nového projektu.  
  
 Tato funkce je podobná [SccGetProjPath](../extensibility/sccgetprojpath-function.md), s tím rozdílem, že bezobslužně vytvoří projektu místo výzvy k výběru jedné. Když `SccCreateSubProject` funkce je volána, `lpParentProjName` a `lpAuxProjPath` nesmí být prázdný a bude odpovídat na platný projekt. Tyto řetězce jsou obvykle přijímány IDE z předchozího volání `SccGetProjPath` funkce nebo [SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md).  
  
 `lpUser` Argument je uživatelské jméno. Prostředí IDE předá ve stejné uživatelské jméno, který byl dříve získali od `SccGetProjPath`, a modul plug-in zdrojového kódu má použít jako výchozí název. Pokud uživatel už má otevřené připojení s modulem plug-in, modul plug-in musí opakujte omezit zobrazování výzev a ujistěte se, že funkce funguje bez upozornění. Ale pokud přihlášení selže, modul plug-in by se zobrazit výzva uživatele pro přihlášení, když obdrží platného přihlášení, předejte název zpět na `lpUser`. Protože modul plug-in může změnit tento řetězec, rozhraní IDE vždy přidělit vyrovnávací paměť o velikosti (SCC_USER_LEN + 1 nebo SCC_USER_SIZE, včetně místa pro ukončení null). Pokud řetězec změnil, nový řetězec musí být platným přihlašovacím jménem (alespoň jako platná jako původní řetězec).  
  
## <a name="technical-notes-for-scccreatesubproject-and-sccgetparentprojectpath"></a>Technické poznámky pro SccCreateSubProject a SccGetParentProjectPath  
 Přidání řešení a projekty do správy zdrojového kódu je jednodušší v sadě Visual Studio, chcete-li minimalizovat počet, který je uživatel vyzván k výběru umístění v systému správy zdrojů. Tyto změny jsou aktivované pomocí sady Visual Studio, pokud modul plug-in správy zdroje podporuje i nové funkce, `SccCreateSubProject` a `SccGetParentProjectPath`. Následující položky registru však lze zakázat tyto změny a obnovit předchozí chování sady Visual Studio (Zdroj ovládacího prvku Plug-in rozhraní API verze 1.1):  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateSolutionRootFolderInSourceControl" = dword: 00000001  
  
 Pokud tato položka registru neexistuje nebo je nastaven na DWORD: 00000000, Visual Studio se pokusí použít nové funkce, `SccCreateSubProject` a `SccGetParentProjectPath`.  
  
 Pokud je položka registru nastavena na DWORD: 00000001, Visual Studio nebude pokoušet použít tyto nové funkce a operace přidání do správy zdrojového kódu fungují stejně jako v předchozích verzích sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md)   
 [SccGetProjPath](../extensibility/sccgetprojpath-function.md)