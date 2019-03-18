---
title: IDebugProperty::GetExtendedInfo | Dokumentace společnosti Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 707474f786a8f88c0e08d887f2c2b09c8aaedc8e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58144859"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
Získá rozšířené informace o vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cInfos`  
 [in] Počet objektů rozšířené informace, které.  
  
 `rgguidExtendedInfo`  
 [in] Pole `GUID`s se předává tak, aby více položek rozšířené informace mohou být načteny současně.  
  
 `pExtendedInfo`  
 [out] Vrátí pole `VARIANT`, které slouží k načtení informací o rozšířené vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní získá rozšířené informace pro tento objekt. Rozhraní API existuje pouze za účelem načtení informací, které se nepropůjčuje pro načtení pomocí `IDebugProperty::GetPropertyInfo`).  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)