---
title: IActiveScriptSiteDebug32::GetDocumentContextFromPosition | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53348dff-35a6-4303-b263-90c10af06bf3
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 9a52abcfa4defb49526f944469c95a2247f5d85c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992518"
---
# <a name="iactivescriptsitedebug32getdocumentcontextfromposition"></a>IActiveScriptSiteDebug32::GetDocumentContextFromPosition
Použít modul jazyka delegovat `IDebugCodeContext::GetSourceContext`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDocumentContextFromPosition(  
   DWORD_PTR                dwSourceContext,  
   ULONG                    uCharacterOffset,  
   ULONG                    uNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwSourceContext`  
 [in] Zdrojový obsah poskytnete `ParseScriptText` nebo `AddScriptlet`.  
  
 `uCharacterOffset`  
 [in] Znak posun vzhledem k začátku bloku skriptu nebo skriptletu.  
  
 `uNumChars`  
 [in] Počet znaků v tomto kontextu.  
  
 `ppsc`  
 [out] Kontext dokumentu, který odpovídá této pozici znaku rozsahu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Jazyk moduly pomocí této metody můžete delegovat `IDebugCodeContext::GetSourceContext`.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSiteDebug32 – rozhraní](../../winscript/reference/iactivescriptsitedebug32-interface.md)