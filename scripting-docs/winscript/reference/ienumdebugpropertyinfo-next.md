---
title: IEnumDebugPropertyInfo::Next | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugPropertyInfo.Next
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugPropertyInfo::Next
ms.assetid: 052837ac-1599-49cc-9a5a-ba90f992eeff
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 24835d4d17cacae44a3eb4593b6292ada4672ccb
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096366"
---
# <a name="ienumdebugpropertyinfonext"></a>IEnumDebugPropertyInfo::Next
Načte zadaný počet `DebugPropertyInfo` struktury v sekvenci výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Next (  
   ULONGcelt,  
   DebugPropertyInfo*rgelt,  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet `DebugPropertyInfo`struktury, která se má načíst.  
  
 `rgelt`  
 [out] Pole `DebugPropertyInfo` struktury načíst.  
  
 `pceltFetched`  
 [out] Vrátí počet `DebugPropertyInfo` struktury, ve skutečnosti načíst.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Ienumdebugpropertyinfo – rozhraní](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [DebugPropertyInfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)