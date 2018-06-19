---
title: IDebugExtendedProperty::EnumExtendedMembers | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 81b1cbb9b36d7ae237551aad2677f9480c615b88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794283"
---
# <a name="idebugextendedpropertyenumextendedmembers"></a>IDebugExtendedProperty::EnumExtendedMembers
Vytvoří výčet členů rozšířené vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumExtendedMembers(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   IEnumDebugExtendedPropertyInfo**  ppeepi  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [v] Určuje, že EX_DBGPROP_INFO_FLAGS konstanty, které určují, že pole v výčtové rozšířené vlastnosti struktury ladění který mají být vyplněna.  
  
 `nRadix`  
 [v] Základ – který se má použít při interpretaci všechny číselné informace.  
  
 `ppeepi`  
 [out] Vrátí `IEnumDebugExtendedPropertyInfo` rozhraní, které se zobrazí vlastnosti člena.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugextendedproperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX_DBGPROP_INFO_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [Extendeddebugpropertyinfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)