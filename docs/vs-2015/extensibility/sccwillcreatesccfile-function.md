---
title: Sccwillcreatesccfile – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccWillCreateSccFile
helpviewer_keywords:
- SccWillCreateSccFile function
ms.assetid: 0d7542f0-4351-41b3-b24c-960ab99c05a1
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cb0df475098a0fb0675327cece6dd9c643a0c4d7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54785034"
---
# <a name="sccwillcreatesccfile-function"></a>SccWillCreateSccFile – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce určí, zda modul plug-in správy zdrojového kódu podporuje vytváření MSSCCPRJ. Soubor SCC pro každou z dané soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccWillCreateSccFile(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPBOOL  pbSccFiles  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 %{nfiles/  
 [in] Počet názvů souborů, které jsou součástí `lpFileNames` pole a délky `pbSccFiles` pole.  
  
 lpFileNames  
 [in] Pole názvů úplný soubor ke kontrole (pole přidělené volajícímu).  
  
 pbSccFiles  
 [out v] Pole, ve kterém můžete ukládat výsledky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěch.|  
|SCC_E_INVALIDFILEPATH|Jedna z cest v poli je neplatný.|  
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je volána s seznam souborů k určení, pokud modul plug-in správy zdrojového kódu poskytuje podporu v MSSCCPRJ. Soubor SCC pro každou z dané soubory (pro další informace o MSSCCPRJ. Soubor SCC, naleznete v tématu [MSSCCPRJ. Soubor SCC](../extensibility/mssccprj-scc-file.md)). Ovládací prvek moduly plug-in zdrojového kódu můžete deklarovat, zda mají možnost vytvoření MSSCCPRJ. Soubory SCC deklarováním `SCC_CAP_SCCFILE` během inicializace. Modul plug-in vrátí `TRUE` nebo `FALSE` každý soubor `pbSccFiles` pole k označení, která dané soubory mají MSSCCPRJ. Podpora SCC. Pokud modul plug-in vrátí kód úspěšnosti z funkce, jsou hodnoty v poli návratový dodržena. Při selhání pole se ignoruje.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Soubor MSSCCPRJ.SCC](../extensibility/mssccprj-scc-file.md)
