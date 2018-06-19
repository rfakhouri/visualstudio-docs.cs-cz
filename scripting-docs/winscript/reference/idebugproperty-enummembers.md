---
title: IDebugProperty::EnumMembers | Microsoft Docs
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
ms.openlocfilehash: 9cb57f2609fcd9a80e2a9e0dfd63637e6f700047
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794415"
---
# <a name="idebugpropertyenummembers"></a>IDebugProperty::EnumMembers
Vytvoří výčet členů vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumMembers (  
   DBGPROP_INFO_FLAGSdwFieldSpec,  
   UINTnRadix,  
   REFIIDrefiid,  
   IEnumDebugPropertyInfo**ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [v] Určuje, `DBGPROP_INFO_FLAGS` konstanty, které určují, která pole v struktury vlastnost výčtové ladění jsou k vyplnění.  
  
 `nRadix`  
 [v] Základ – který se má použít při interpretaci všechny číselné informace.  
  
 `refiid`  
 [v] Tento identifikátor IID byla předána pro filtrování enumerátor. Identifikátory IID je jedním z `IDebugPropertyEnumType` rozhraní, které dědí od `IDebugPropertyEnumType_All`.  
  
 `ppEnum`  
 [out] Vrátí `IEnumDebugPropertyInfo` rozhraní, které se zobrazí vlastnosti člena.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)   
 [Idebugpropertyenumtype_all – rozhraní](../../winscript/reference/idebugpropertyenumtype-all-interface.md)   
 [Ienumdebugpropertyinfo – rozhraní](../../winscript/reference/ienumdebugpropertyinfo-interface.md)