---
title: IDebugObject2::IsUserData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8c20b4e531284156b8790b1ca65b32c85d1db997
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112282"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
Určuje, zda objekt představuje data uživatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pfUser`  
 [out] Vrátí nenulovou hodnotu (`TRUE`), pokud objekt představuje data uživatele; hodnotu (`FALSE`) Pokud tomu tak není.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Uživatelská data je libovolný objekt, který je součástí modulu určený jako JustMyCode (uživatelsky konfigurovatelného možnost, která označuje modulu, jako uživatelský kód a proto viditelné v trasování zásobníku).  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)