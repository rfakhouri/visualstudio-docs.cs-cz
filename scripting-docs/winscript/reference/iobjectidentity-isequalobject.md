---
title: IObjectIdentity::IsEqualObject | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IObjectIdentity.IsEqualObject
apilocation:
- scrobj.dll
helpviewer_keywords:
- IsEqualObject method
ms.assetid: 78c5c5c2-d299-4036-986c-7c1d87cbe7cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa233e478c83b723b13d19d27dc4b63ee4700bb5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095053"
---
# <a name="iobjectidentityisequalobject"></a>IObjectIdentity::IsEqualObject
Určuje, zda je objekt rovná aktuálnímu objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT IsEqualObject(  
  IUnknown*punk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `punk`  
 [in] Adresa objektu má být porovnán s aktuální objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Objekty jsou si rovny.|  
|`S_FALSE`|Objekty nejsou stejné.|  
  
## <a name="remarks"></a>Poznámky  
 Implementace `IsEqualObject` metoda by měla vrátit `S_OK` pouze v případě, objekty jsou identické.  
  
## <a name="see-also"></a>Viz také  
 [IObjectIdentity – rozhraní](../../winscript/reference/iobjectidentity-interface.md)