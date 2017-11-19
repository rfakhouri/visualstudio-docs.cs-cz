---
title: Funkce SccInitialize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccInitialize
helpviewer_keywords: SccInitialize function
ms.assetid: 5bc0d28b-2c68-4d43-9e51-541506a8f76e
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9e688d30d2367236cfcf5b2d14b36eb602832fc0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sccinitialize-function"></a>SccInitialize – funkce
Tato funkce inicializuje modul plug-in zdrojového kódu a poskytuje možnosti a omezení na integrované vývojové prostředí (IDE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccInitialize (  
   LPVOID* ppvContext,  
   HWND    hWnd,  
   LPCSTR  lpCallerName,  
   LPSTR   lpSccName,  
   LPLONG  lpSccCaps,  
   LPSTR   lpAuxPathLabel,  
   LPLONG  pnCheckoutCommentLen,  
   LPLONG  pnCommentLen  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppvContext`  
 [v] Správa zdrojového kódu modul plug-in můžete sem umístěte ukazatel na strukturu jeho kontextu.  
  
 `hWnd`  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 `lpCallerName`  
 [v] Název programu volání modulu plug-in zdrojového kódu.  
  
 `lpSccName`  
 [ve out] Vyrovnávací paměti, které modul plug-in zdrojového kódu vloží svůj vlastní název (není k překročení `SCC_NAME_LEN`).  
  
 `lpSccCaps`  
 [out] Vrátí plug-in příznaky funkce zdrojového kódu.  
  
 `lpAuxPathLabel`  
 [ve out] Vyrovnávací paměti, které modul plug-in zdrojového kódu vloží řetězec, který popisuje `lpAuxProjPath` parametr vrácený [SccOpenProject](../extensibility/sccopenproject-function.md) a [SccGetProjPath](../extensibility/sccgetprojpath-function.md) (nepřesahující `SCC_AUXLABEL_LEN`).  
  
 `pnCheckoutCommentLen`  
 [out] Vrátí maximální povolenou délku najdete v článku věnovaném komentář.  
  
 `pnCommentLen`  
 [out] Vrátí maximální povolenou délku pro ostatní komentáře.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Inicializace řízení zdroj bylo úspěšné.|  
|SCC_E_INITIALIZEFAILED|Nepodařilo se inicializovat systému.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést zadanou operaci.|  
|SCC_E_NONSPECFICERROR|Nespecifikované chybě; správy zdrojového kódu se neinicializoval.|  
  
## <a name="remarks"></a>Poznámky  
 Prostředí IDE volá tuto funkci, pokud nejprve načte modul plug-in zdrojového kódu. Umožňuje IDE předávat určité informace, například název volajícího, v modulu plug-in. Prostředí IDE zpět také získá určité informace, jako je například maximální povolenou délku komentáře a jejich plug v společnosti.  
  
 `ppvContext` Odkazuje na `NULL` ukazatel. Správa zdrojového kódu modul plug-in můžete přidělit strukturu pro vlastní použití a Uložit ukazatel na této struktury v `ppvContext`. Prostředí IDE předá tento ukazatel všechny ostatní funkce rozhraní API VSSCI, povolení modulu plug-in tak, aby měl k dispozici informace o kontextu bez nutnosti globální úložiště a k podpoře více instancí modulu plug-in. Tato struktura by měl být navrácena při [SccUninitialize](../extensibility/sccuninitialize-function.md) je volána.  
  
 `lpCallerName` a `lpSccName` parametry povolit IDE a modul plug-in zdrojového kódu pro výměnu názvy. Názvy těchto může být použit k rozlišení mezi více instancí, nebo může ve skutečnosti se v nabídkách a dialogových oknech.  
  
 `lpAuxPathLabel` Parametr je použit jako komentář k identifikaci cesty pomocného projektu, který je uložený v souboru řešení a předaný zdrojového kódu ve volání modulu plug-in řetězec [SccOpenProject](../extensibility/sccopenproject-function.md). [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)]použije řetězec "projektu SourceSafe:"; Další zdroje řízení moduly plug-in neměly by pomocí tohoto konkrétního řetězce.  
  
 `lpSccCaps` Parametr dává zdrojového kódu modulu plug-in místo pro uložení bitové příznaky označující plug v na možnosti. (Úplný seznam bitové příznaky schopností najdete v tématu [schopností příznaky](../extensibility/capability-flags.md)). Například pokud modul plug-in plány zapsat výsledky do funkce zpětného volání zadaný volajícího, modul plug-in byste měli nastavit možnosti bit SCC_CAP_TEXTOUT. To by signál IDE vytvoření okna pro ovládací prvek výsledků verze.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [Příznaky schopností](../extensibility/capability-flags.md)