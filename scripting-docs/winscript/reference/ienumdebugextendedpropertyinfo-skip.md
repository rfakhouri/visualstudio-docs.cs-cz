---
title: IEnumDebugExtendedPropertyInfo::Skip | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Skip
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Skip
ms.assetid: a0b4a9fc-e122-482b-9384-b83c460b61fe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cc88f41e1c75a2b6616cc6aba363b8824605a696
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345289"
---
# <a name="ienumdebugextendedpropertyinfoskip"></a>IEnumDebugExtendedPropertyInfo::Skip
Vynechá zadaný počet `ExtendedDebugPropertyInfo` struktury v sekvenci výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Skip(  
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet `ExtendedDebugPropertyInfo` struktury v pořadí výčtu pro přeskočení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`. Vrátí `S_FALSE` a nastaví aktuální ukazatel na prvek na konci výčtu, pokud `celt` je větší než počet elementů vlevo v enumerátor.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugExtendedPropertyInfo Interface](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [ExtendedDebugPropertyInfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)