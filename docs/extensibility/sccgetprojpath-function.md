---
title: Funkce SccGetProjPath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetProjPath
helpviewer_keywords: SccGetProjPath function
ms.assetid: 1079847e-d45f-4cb8-9d92-1e01ce5d08f6
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7c626cfc6da56258241071476aba03690f349092
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sccgetprojpath-function"></a>SccGetProjPath – funkce
Tato funkce zobrazí výzvu pro cestu k projektu, který je řetězec, který má smysl pouze na modul plug-in zdrojového kódu. Je volána, pokud je uživatel:  
  
-   Vytvoření nového projektu  
  
-   Přidání existujícího projektu do správy verzí  
  
-   Probíhá pokus o vyhledání existujícího projektu řízení verze  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGetProjPath (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPSTR  lpUser,  
   LPSTR  lpProjName,  
   LPSTR  lpLocalPath,  
   LPSTR  lpAuxProjPath,  
   BOOL   bAllowChangePath,  
   LPBOOL pbNew  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpUser  
 [ve out] Uživatelské jméno (nesmí přesáhnout SCC_USER_SIZE, včetně ukončení NULL)  
  
 lpProjName  
 [ve out] Název projektu IDE, pracovní prostor projektu nebo souboru pravidel (nesmí přesáhnout SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 lpLocalPath  
 [ve out] Cesta pracovního projektu. Pokud `bAllowChangePath` je `TRUE`, modul plug-in zdrojového kódu můžete upravit tento řetězec (nesmí přesáhnout _max_path –, včetně ukončení null).  
  
 lpAuxProjPath  
 [ve out] Vyrovnávací paměť pro cestu vrácený projektu (nesmí přesáhnout SCC_PRJPATH_SIZE, včetně ukončení NULL).  
  
 bAllowChangePath  
 [v] Pokud je to `TRUE`, modul plug-in zdrojového kódu můžete vyzvat k zadání a upravit `lpLocalPath` řetězec.  
  
 pbNew  
 [ve out] Hodnota brzo označuje, zda chcete-li vytvořit nový projekt. Hodnota vrácená označuje úspěch pro vytvoření projektu:  
  
|příchozí|Interpretace|  
|--------------|--------------------|  
|HODNOTA TRUE|Uživatel může vytvořit nový projekt.|  
|FALSE|Uživatele nelze vytvořit nový projekt.|  
  
|Odchozí|Interpretace|  
|--------------|--------------------|  
|HODNOTA TRUE|Byl vytvořen nový projekt.|  
|FALSE|Nebyla vybrána existující projekt.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Projekt byl úspěšně vytvořil nebo načíst.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí.|  
|SCC_E_CONNECTIONFAILURE|Došlo k potížím při pokusu o připojení k systému správy zdrojů.|  
|SCC_E_NONSPECIFICERROR|Došlo k neurčené chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Účelem této funkce je pro IDE získat parametry `lpProjName` a `lpAuxProjPath`. Po modul plug-in správy zdroje výzvu k zadání těchto informací, předá tyto dva řetězce zpět do prostředí IDE. Prostředí IDE potrvají tyto řetězce v souboru jeho řešení a předá je [SccOpenProject](../extensibility/sccopenproject-function.md) vždy, když uživatel otevře tento projekt. Tyto řetězce povolit modul plug-in pro sledování informace související s projektem.  
  
 Když je volána funkce nejprve `lpAuxProjPath` nastavena na prázdný řetězec. `lProjName`je také možné prázdná, nebo může obsahovat název projektu IDE, které modul plug-in správy zdroje může použít nebo ignorovat. Při funkce úspěšně vrátí hodnotu, modul plug-in vrátí dva odpovídající řetězce. Prostředí IDE nemá žádné předpoklady o tyto řetězce, nebude používat a nebude povolit uživateli je upravit. Pokud uživatel chce změnit nastavení, bude volat rozhraní IDE `SccGetProjPath` znovu předávání stejné hodnoty, které je v minulosti obdržel předchozí čas. To dává modulu plug-in plnou kontrolu nad tyto dva řetězce.  
  
 Pro `lpUser`, uživatelské jméno může předat rozhraní IDE nebo jej může jednoduše předat ukazatel na prázdný řetězec. Pokud je uživatelské jméno, modul plug-in zdrojového kódu má použít jako výchozí. Ale pokud nebyl předán žádný název, nebo pokud se přihlášení nezdařilo se zadaným názvem, modul plug-in by se zobrazit výzva uživatele k přihlášení a předejte název zpět na `lpUser` při přijetí platného přihlášení. Protože modul plug-in může změnit tento řetězec, rozhraní IDE vždy přidělit vyrovnávací paměť o velikosti (`SCC_USER_LEN`+ 1).  
  
> [!NOTE]
>  První akci, která provádí integrovaného vývojového prostředí může být buď volání `SccOpenProject` funkce nebo `SccGetProjPath` funkce. Proto z nich mají identická `lpUser` parametr, který umožňuje modul plug-in přihlásit uživatele buď během zdrojového kódu. I když vrátit z funkce znamená chybu, musí modulu plug-in zadejte tento řetězec s platným přihlašovacím jménem.  
  
 `lpLocalPath`je adresář, kde uživatel udržuje projektu. To může být prázdný řetězec. Pokud neexistuje žádný adresář aktuálně definován (jako v případě uživatel pokus o stažení projektu ze správy zdrojového kódu) a pokud `bAllowChangePath` je `TRUE`, modul plug-in zdrojového kódu můžete zobrazit výzvu uživateli pro vstup nebo použít jiné metody umístit jeho vlastní řetězec do `lpLocalPath`. Pokud `bAllowChangePath` je `FALSE`, modul plug-in neměli měnit řetězci, protože uživatel pracuje v zadaný adresář již.  
  
 Pokud se uživatel vytvoří nový projekt k uvedení v části Správa zdrojového kódu, modul plug-in správy zdroje nemusí vytvořit ve skutečnosti v systému správy zdrojového kódu v době `SccGetProjPath` je volána. Místo toho předá zpět řetězec společně s nenulovou hodnotu pro `pbNew`, která určuje, že projektu budou vytvořeny v systému správy zdrojů.  
  
 Například, pokud uživatel ve **nový projekt** průvodce v sadě Visual Studio přidá svůj projekt do správy zdrojového kódu, volá tuto funkci, Visual Studio a určuje modul plug-in, pokud je to v pořádku v systému správy zdrojů pro vytvoření nového projektu obsahovat projektu sady Visual Studio. Pokud uživatel klikne na **zrušit** před dokončením průvodce, nikdy vytvoření projektu. Pokud uživatel klikne na **OK**, Visual Studio volá `SccOpenProject`a předejte `SCC_OPT_CREATEIFNEW`, a vytvoření projektu zdroj řídí v daném čase.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)