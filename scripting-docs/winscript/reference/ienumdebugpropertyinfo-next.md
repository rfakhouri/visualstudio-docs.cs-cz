---
title: IEnumDebugPropertyInfo::Next | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IEnumDebugPropertyInfo.Next
apilocation: scrobj.dll
helpviewer_keywords: IEnumDebugPropertyInfo::Next
ms.assetid: 052837ac-1599-49cc-9a5a-ba90f992eeff
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bc1e25a865ab1e21ab011e3a5bd0cc3b74f4abf2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="ienumdebugpropertyinfonext"></a>IEnumDebugPropertyInfo::Next
Načte zadaný počet `DebugPropertyInfo` struktury v posloupnosti výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Next (  
   ULONGcelt,  
   DebugPropertyInfo*rgelt,  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet `DebugPropertyInfo`struktury mají být načteny.  
  
 `rgelt`  
 [out] Pole `DebugPropertyInfo` struktury načíst.  
  
 `pceltFetched`  
 [out] Vrátí počet `DebugPropertyInfo` struktury, ve skutečnosti načíst.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Ienumdebugpropertyinfo – rozhraní](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [Debugpropertyinfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)