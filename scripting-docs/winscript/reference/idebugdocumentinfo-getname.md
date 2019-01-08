---
title: IDebugDocumentInfo::GetName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: f3ecde4fbde1a265596a01d7f0f953763363e797
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097692"
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
 [Idebugdocumentinfo – rozhraní](../../winscript/reference/idebugdocumentinfo-interface.md)   
 [DOCUMENTNAMETYPE – výčet](../../winscript/reference/documentnametype-enumeration.md)