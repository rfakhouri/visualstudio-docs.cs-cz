---
title: POPDIRLISTFUNC | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 37643aecf5e106c84121008423a391f8075c76fc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55005615"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
Toto je funkce zpětného volání k [sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md) funkce se aktualizovat kolekci adresářů a (volitelně) názvy souborů a zjistěte, které jsou pod správou zdrojových kódů.  
  
 `POPDIRLISTFUNC` Zpětného volání lze volat pouze pro tyto adresáře a názvy souborů (v seznamu udělená `SccPopulateDirList` funkce), které jsou ve skutečnosti pod správou zdrojových kódů.  
  
## <a name="signature"></a>podpis  
  
```cpp  
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
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Pokračujte ve zpracování.|  
|SCC_I_OPERATIONCANCELED|Zastavte zpracování.|  
|SCC_E_xxx|Všechny chyby příslušný zdrojový ovládací prvek by se měla zastavit zpracování.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud `fOptions` parametr `SccPopulateDirList` obsahuje funkce `SCC_PDL_INCLUDEFILES` příznak, bude pravděpodobně obsahovat seznam názvů souborů, jakož i názvy adresářů.  
  
## <a name="see-also"></a>Viz také:  
 [Funkce zpětného volání implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [Kódy chyb](../extensibility/error-codes.md)