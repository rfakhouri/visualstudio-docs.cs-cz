---
title: IDebugFormatter::GetStringForVariant | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugFormatter.GetStringForVariant
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugFormatter::GetStringForVariant
ms.assetid: 95189d03-1126-433e-8513-659107b3df16
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 901bf9648d4d16faf7386b528cc3fd877070a5b6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996854"
---
# <a name="idebugformattergetstringforvariant"></a>IDebugFormatter::GetStringForVariant
Vrátí řetězec, který představuje dané hodnoty hodnotu typu VARIANT.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetStringForVariant(  
   VARIANT*  pvar,  
   ULONG     nRadix,  
   BSTR*     pbstrValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvar`  
 [in] VARIANTA pro reprezentaci jako řetězec.  
  
 `nRadix`  
 [in] Číselná soustava k použití pro číselné hodnoty.  
  
 `pbstrValue`  
 [out] Řetězec představující `pvar`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí řetězec, který představuje dané hodnoty hodnotu typu variant.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFormatter – rozhraní](../../winscript/reference/idebugformatter-interface.md)