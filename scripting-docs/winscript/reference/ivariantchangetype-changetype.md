---
title: IVariantChangeType::ChangeType | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IVariantChangeType.ChangeType
apilocation:
- scrobj.dll
helpviewer_keywords:
- IVariantChangeType::ChangeType
ms.assetid: 52374764-c42e-49af-a219-ee00c535a118
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81ed0a8502e9b0cfc53725621d477d34ee5010ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945630"
---
# <a name="ivariantchangetypechangetype"></a>IVariantChangeType::ChangeType
Vezme hodnotu typu variant a vytvoří novou variantu pomocí zadaného typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ChangeType(  
   VARIANT*  pvarDst,  
   VARIANT*  pvarSrc,  
   LCID  lcid,  
   VARTYPE  vtNew  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvarDst`  
 [out v] Hodnotu typu variant obsahující Hodnota reprezentovaná `pvarSrc`, ale v typu zadaném pomocí `vtNew`.  
  
 `pvarSrc`  
 [in] Varianty hodnota změny do nového typu.  
  
 `lcid`  
 [in] Kontext národního prostředí, který se má použít při převodu argumentů do nebo z řetězce.  
  
 `vtNew`  
 [in] Určuje typ `pvarDst` stát.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 `pvarDst` a `pvarSrc` argumenty mohou být stejné, v takovém případě se přepíše původní hodnotu. Tato metoda předává `pvarDst` k `VariantClear` funkce a proto `pvarDst` by se měl inicializovat na platnou hodnotu.  
  
## <a name="see-also"></a>Viz také  
 [IVariantChangeType – rozhraní](../../winscript/reference/ivariantchangetype-interface.md)