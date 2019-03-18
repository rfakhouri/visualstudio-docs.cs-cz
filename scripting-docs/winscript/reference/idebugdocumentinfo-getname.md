---
title: IDebugDocumentInfo::GetName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentInfo.GetName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentInfo::GetName
ms.assetid: c25d73da-99b6-4c9f-82af-182b4853f81c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9975563c27b986190fbd2731c3f36b1e32719c0b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160323"
---
# <a name="idebugdocumentinfogetname"></a>IDebugDocumentInfo::GetName
Vrátí zadaný název dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetName(  
   DOCUMENTNAMETYPE  dnt,  
   BSTR*             pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dnt`  
 [in] Zadejte název dokumentu vrátit.  
  
 `pbstrName`  
 [out] Řetězec obsahující název.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Zadaný název dokumentu není znám.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrací zadaný název dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentInfo Interface](../../winscript/reference/idebugdocumentinfo-interface.md)   
 [DOCUMENTNAMETYPE – výčet](../../winscript/reference/documentnametype-enumeration.md)