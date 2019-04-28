---
title: IDebugExtendedProperty::EnumExtendedMembers | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExtendedProperty.EnumExtendedMembers
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugExtendedProperty::EnumExtendedMembers
ms.assetid: 27cdb091-da4e-44d2-a631-31ae00468b98
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c7e14d1bc8937221960d938f1bbfae8e307830f2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946142"
---
# <a name="idebugextendedpropertyenumextendedmembers"></a>IDebugExtendedProperty::EnumExtendedMembers
Vytvoří výčet členy rozšířené vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumExtendedMembers(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   IEnumDebugExtendedPropertyInfo**  ppeepi  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [in] Určuje, že EX_DBGPROP_INFO_FLAGS konstanty, které určují, že pole výčet Rozšířené ladicí vlastnosti struktury, která mají být vyplněna.  
  
 `nRadix`  
 [in] Základ, který se má použít při interpretaci jakékoli číselné informace.  
  
 `ppeepi`  
 [out] Vrátí `IEnumDebugExtendedPropertyInfo` rozhraní, které zobrazuje výčet vlastností člena.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugextendedproperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX_DBGPROP_INFO_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [ExtendedDebugPropertyInfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)