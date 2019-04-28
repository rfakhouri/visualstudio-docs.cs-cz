---
title: IActiveScriptAuthor::GetChars | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetChars
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetChars
ms.assetid: a73ba263-12f7-4d5f-b4c8-9ad7e2d5d3cb
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 69cdeb16fa0791b3ff8c0cce4a4e67fe110eefc2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935370"
---
# <a name="iactivescriptauthorgetchars"></a>IActiveScriptAuthor::GetChars
Vrátí sadu znaků dokončení pro dokončení požadované kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetChars(  
   DWORD            fRequestedList,  
   BSTR             *pbstrChars  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fRequestedList`  
 [in] Kontext požadovaný dokončení.  
  
|Konstanta|Value|Popis|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_ENUM_TRIGGER|0x0001|Požadavky levé straně výčtu.|  
|SCRIPT_CMPL_MEMBER_TRIGGER|0x0002|Požádá o dokončení kontextu člena.|  
|SCRIPT_CMPL_PARAM_TRIGGER|0x0003|Vyžádá seznam parametrů.|  
|SCRIPT_CMPL_COMMIT|0x0004|Požadavky na konce seznamu parametrů.|  
  
 `pbstrChars`  
 [out] Znaky, které odpovídají kontext požadovaný dokončení.  
  
|`fRequestedList` Parametr|Vrátí znaky|  
|--------------------------------|-------------------------|  
|SCRIPT_CMPL_ENUM_TRIGGER|"."|  
|SCRIPT_CMPL_MEMBER_TRIGGER|"="|  
|SCRIPT_CMPL_PARAM_TRIGGER|"(,"|  
|SCRIPT_CMPL_COMMIT|"()"|  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)