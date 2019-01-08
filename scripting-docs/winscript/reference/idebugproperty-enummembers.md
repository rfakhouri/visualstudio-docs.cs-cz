---
title: IDebugProperty::EnumMembers | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.EnumMembers
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::EnumMembers
ms.assetid: 8ce398a5-6452-4804-ae8f-5c54cd11c661
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7edf2d2f94519146a81cf94b3bf30946af59bbe9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097029"
---
# <a name="idebugpropertyenummembers"></a>IDebugProperty::EnumMembers
Vytvoří výčet členů vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumMembers (  
   DBGPROP_INFO_FLAGSdwFieldSpec,  
   UINTnRadix,  
   REFIIDrefiid,  
   IEnumDebugPropertyInfo**ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [in] Určuje, `DBGPROP_INFO_FLAGS` konstanty, které určují pole ve strukturách vlastnost výčtu ladění, která mají být vyplněna.  
  
 `nRadix`  
 [in] Základ, který se má použít při interpretaci jakékoli číselné informace.  
  
 `refiid`  
 [in] Tento IID je předán pro filtrování enumerátor. Identifikátor IID je jedním z `IDebugPropertyEnumType` rozhraní, která dědí z `IDebugPropertyEnumType_All`.  
  
 `ppEnum`  
 [out] Vrátí `IEnumDebugPropertyInfo` rozhraní, které zobrazuje výčet vlastností člena.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)   
 [Idebugpropertyenumtype_all – rozhraní](../../winscript/reference/idebugpropertyenumtype-all-interface.md)   
 [IEnumDebugPropertyInfo – rozhraní](../../winscript/reference/ienumdebugpropertyinfo-interface.md)