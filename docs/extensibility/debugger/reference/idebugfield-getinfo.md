---
title: IDebugField::GetInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6738306abd991062c5091f95375972ffe0d3384e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
Tato metoda získá zobrazitelné informace o pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetInfo(   
   FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO* pFieldInfo  
);  
```  
  
```csharp  
int GetInfo(  
   enum_FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO[] pFieldInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFields`  
 [v] Kombinace [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) konstanty, které vybere zobrazit informace. Pokud toto pole představuje symbol, to je obvykle symbol názvem a typem.  
  
 `pFieldInfo`  
 [out] Vrátí informace do zadané [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) struktury.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)