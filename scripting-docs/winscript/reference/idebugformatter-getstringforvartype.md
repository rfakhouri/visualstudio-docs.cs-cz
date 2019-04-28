---
title: IDebugFormatter::GetStringForVarType | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugFormatter.GetStringForVarType
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugFormatter::GetStringForVarType
ms.assetid: 1c1a0499-ca57-47e0-8367-fdb4c902bca3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d83df97ac9cb6c38d989470b71da93aceb5d50b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979211"
---
# <a name="idebugformattergetstringforvartype"></a>IDebugFormatter::GetStringForVarType
Vrátí řetězec, který představuje dané hodnota VARTYPE.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetStringForVarType(  
   VARTYPE    vt,  
   TYPEDESC*  ptdescArrayType,  
   BSTR*      pbstr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `vt`  
 [in] VARTYPE k reprezentaci jako řetězec.  
  
 `ptdescArrayType`  
 [in] Pole struktur, které popisují typy.  
  
 `pbstr`  
 [out] Řetězec představující `vt`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Metoda vrátí řetězec, který představuje dané hodnota VARTYPE.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFormatter – rozhraní](../../winscript/reference/idebugformatter-interface.md)