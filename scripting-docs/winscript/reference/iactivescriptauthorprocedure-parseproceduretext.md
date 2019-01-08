---
title: IActiveScriptAuthorProcedure::ParseProcedureText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthorProcedure.ParseProcedureText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthorProcedure::ParseProcedureText
ms.assetid: cb6c29c5-c749-48d7-a6a8-ccbf0f9119ec
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 893dc36c066426ad1de7346c7ce1fea24b191ba3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090685"
---
# <a name="iactivescriptauthorprocedureparseproceduretext"></a>IActiveScriptAuthorProcedure::ParseProcedureText
Analyzuje kód procedury, přidá kód procedury text skriptu pro vytváření modulu a vytvoří `IScriptEntry` objekt, který odpovídá kódu procedury.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ParseProcedureText(  
   LPCOLESTR   pszCode,  
   LPCOLESTR   pszFormalParams,  
   LPCOLESTR   pszProcedureName,  
   LPCOLESTR   pszItemName,  
   LPCOLESTR   pszDelimiter,  
   DWORD       dwCookie,  
   DWORD       dwFlags,  
   IDispatch   *pdispFor  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCode`  
 [in] Text skriptu k analýze.  
  
 `pszFormalParams`  
 [in] Adresa názvy formálních parametrů pro proceduru. Názvy parametrů musí být odděleny příslušné oddělovače pro skript, modul pro vytváření. Názvy nesmí být uzavřen v závorkách.  
  
 `pszProcedureName`  
 [in] Adresa název procedury, který se má analyzovat.  
  
 `pszItemName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název položky přidružené k `IScriptEntry` objektu.  
  
 `pszDelimiter`  
 [in] Adresa koncového ze skriptu bloku oddělovač. Když `pszCode` je analyzován z toku textu, hostitel obvykle používá oddělovač (například dvěma jednoduchými uvozovkami), k zjištění konce bloku skriptu. Tento parametr nastavte na hodnotu NULL, pokud neexistuje žádný oddělovač pro označení konce bloku skriptu.  
  
 `dwCookie`  
 [in] Hodnotu definované aplikací, který je spojen s novými `IScriptEntry` objektu.  
  
 `dwFlags`  
 [in] Nepoužívá se.  
  
 `pdispFor`  
 [in] Nepoužívá se.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Aktuální [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] modul neimplementuje této metody.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthorProcedure – rozhraní](../../winscript/reference/iactivescriptauthorprocedure-interface.md)