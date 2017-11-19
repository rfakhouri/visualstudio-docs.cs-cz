---
title: IEnumDebugFields::Reset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFields::Reset
helpviewer_keywords: IEnumDebugFields::Reset method
ms.assetid: 38ff61e4-0120-42e8-971a-16be6050b425
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2d443f7b5530349663f8e8fdf63c7ed042a1d2da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugfieldsreset"></a>IEnumDebugFields::Reset
Tato metoda obnoví výčtu první prvek.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Po tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumdebugfields-next.md) vrátí první prvek výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [Další](../../../extensibility/debugger/reference/ienumdebugfields-next.md)