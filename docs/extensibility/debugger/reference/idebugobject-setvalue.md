---
title: IDebugObject::SetValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::SetValue
helpviewer_keywords: IDebugObject::SetValue method
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4e4a4311d5e115e20d23096a6ca1e3bce2dcbea6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobjectsetvalue"></a>IDebugObject::SetValue
Nastaví hodnotu objektu z po sobě jdoucích řady bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int SetValue(  
   byte[] pValue,   
   uint   nSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pValue`  
 [v] Pole bajtů představující novou hodnotu.  
  
 `nSize`  
 [v] Velikost hodnoty v bajtech.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v poli se zkopírují do této [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt, nahraďte všechny stávající hodnotu. Velikost nová hodnota může být větší nebo menší než stávající hodnotu. To `IDebugObject` nemůže být nulová reference.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)