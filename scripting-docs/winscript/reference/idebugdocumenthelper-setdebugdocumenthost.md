---
title: IDebugDocumentHelper::SetDebugDocumentHost | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetDebugDocumentHost
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetDebugDocumentHost
ms.assetid: b26a03c3-8a3f-47b0-b916-4c65d5500f10
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c4a935d849fed2b617abf5ee33ca2901b9c944c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088215"
---
# <a name="idebugdocumenthelpersetdebugdocumenthost"></a>IDebugDocumentHelper::SetDebugDocumentHost
Nastaví `IDebugDocumentHost` pro tento dokument.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetDebugDocumentHost(  
   IDebugDocumentHost*  pddh  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pddh`  
 [in] Dokument hostitele ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 `IDebugDocumentHost` Rozhraní se používá pro barevné zvýrazňování syntaxe smart-host, načítání odložené text a vrátí řízení objektů pro nově vytvořený dokument kontexty.  
  
## <a name="see-also"></a>Viz také  
 [Idebugdocumenthelper – rozhraní](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)