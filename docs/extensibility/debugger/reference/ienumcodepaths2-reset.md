---
title: IEnumCodePaths2::Reset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumCodePaths2::Reset
helpviewer_keywords:
- IEnumCodePaths2::Reset
ms.assetid: 490c0e19-ff4b-4673-bd06-cdee996ac226
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f32c3cef0d92c0f48a765106ee532a3e4992ec4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ienumcodepaths2reset"></a>IEnumCodePaths2::Reset
Obnoví výčtu první prvek.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Po tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumcodepaths2-next.md) metoda vrátí první prvek výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)