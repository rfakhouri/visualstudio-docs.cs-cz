---
title: IActiveScriptSiteDebug::GetDocumentContextFromPosition | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetDocumentContextFromPosition
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetDocumentContextFromPosition
ms.assetid: ba5f7348-0107-4b12-b949-79a012476cf7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1bcc7469e02ba380ebd6839e9fe55031e52ecd32
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086981"
---
# <a name="iactivescriptsitedebuggetdocumentcontextfromposition"></a>IActiveScriptSiteDebug::GetDocumentContextFromPosition
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
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Jazyk moduly pomocí této metody můžete delegovat `IDebugCodeContext::GetSourceContext`.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSiteDebug – rozhraní](../../winscript/reference/iactivescriptsitedebug-interface.md)