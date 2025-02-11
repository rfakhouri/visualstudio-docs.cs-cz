---
title: POPDIRLISTFUNC | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 77e4701d3d8ec54fd37d6483f55b10a28af65b15
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194048"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto je funkce zpětného volání k [sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md) funkce se aktualizovat kolekci adresářů a (volitelně) názvy souborů a zjistěte, které jsou pod správou zdrojových kódů.  
  
 `POPDIRLISTFUNC` Zpětného volání lze volat pouze pro tyto adresáře a názvy souborů (v seznamu udělená `SccPopulateDirList` funkce), které jsou ve skutečnosti pod správou zdrojových kódů.  
  
## <a name="signature"></a>podpis  
  
```cpp#  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>Parametry  
 pvCallerData  
 [in] Hodnota uživatele na [sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md).  
  
 bFolder  
 [in] `TRUE` -li název v `lpDirectoryOrFileName` jedná se o adresář jinak název je název souboru.  
  
 lpDirectoryOrFileName  
 [in] Úplná místní cesta k názvu adresáře nebo souboru, který je pod správou zdrojového kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Rozhraní IDE vrátí odpovídající chybový kód:  
  
|Value|Popis|  
|-----------|-----------------|  
|SCC_OK|Pokračujte ve zpracování.|  
|SCC_I_OPERATIONCANCELED|Zastavte zpracování.|  
|SCC_E_xxx|Všechny chyby příslušný zdrojový ovládací prvek by se měla zastavit zpracování.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud `fOptions` parametr `SccPopulateDirList` obsahuje funkce `SCC_PDL_INCLUDEFILES` příznak, bude pravděpodobně obsahovat seznam názvů souborů, jakož i názvy adresářů.  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [Chybové kódy](../extensibility/error-codes.md)
