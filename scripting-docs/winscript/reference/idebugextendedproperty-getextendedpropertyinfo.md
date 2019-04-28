---
title: IDebugExtendedProperty::GetExtendedPropertyInfo | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExtendedProperty.GetExtendedPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugExtendedProperty::GetExtendedPropertyInfo
ms.assetid: 56edf538-5082-4653-82b6-e6640d6f61ba
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89067720b6643c8c187e6340fb529989f2439933
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946099"
---
# <a name="idebugextendedpropertygetextendedpropertyinfo"></a>IDebugExtendedProperty::GetExtendedPropertyInfo
Načte rozšířené informace o rozšířené vlastnosti, což je více informací, než jednodušší `IDebugProperty`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetExtendedPropertyInfo(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   ExtendedDebugPropertyInfo*  pExtendedPropertyInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [in] Určuje konstanty EX_DBGPROP_INFO_FLAGS, které určují pole pro vyplnění navýšení kapacity `ExtendedDebugPropertyInfo` struktury.  
  
 `nRadix`  
 [in] Základ, který se má použít při interpretaci jakékoli číselné informace.  
  
 `pExtendedPropertyInfo`  
 [out] Vrátí `ExtendedDebugPropertyInfo` struktura, která popisuje vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugextendedproperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX_DBGPROP_INFO_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [ExtendedDebugPropertyInfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)