---
title: IDebugProcess3::GetEngineFilter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GetEngineFilter
- IDebugProcess3::GetEngineFilter
ms.assetid: ccb7ecb0-f189-4e80-b5b2-221a095e01f5
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d6b830a06e5d89a4b9decbdf466cb56db52a4e1f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess3getenginefilter"></a>IDebugProcess3::GetEngineFilter
Načte pole jedinečné identifikátory pro ladění k dispozici moduly.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetEngineFilter(  
   GUID_ARRAY *pEngineArray  
);  
```  
  
```csharp  
public int GetEngineFilter(  
   out GUID_ARRAY[] pEngineArray  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pEngineArray`  
 [out] Odkaz na strukturu, která obsahuje jedinečné identifikátory pro ladění moduly.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [GUID_ARRAY](../../../extensibility/debugger/reference/guid-array.md)