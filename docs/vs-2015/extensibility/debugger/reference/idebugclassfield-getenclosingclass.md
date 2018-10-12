---
title: IDebugClassField::GetEnclosingClass | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ebbfcfbd0fc8d21dfc67193e6e1164e38c923dc
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49225495"
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá třídu, která obklopuje této třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetEnclosingClass(   
   IDebugClassField** ppClassField  
);  
```  
  
```csharp  
int GetEnclosingClass(  
   out IDebugClassField ppClassField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppClassField`  
 [out] Vrátí [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) třídy představující nadřazený objekt. Vrátí hodnotu null, pokud neexistuje žádné nadřazené třídy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud třída představovaného tímto rozhraním [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objektu je vnořená třída, pak bude `ppClassField` vrátí parametr `IDebugClassField` třídy představující nadřazený objekt. Například při této definici třídy:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 Volání `GetEnclosingClass` metodu `IDebugClassField` objekt představující `NestedClass` třídy vrátí `IDebugClassField` objekt představující třídu `RootClass`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)

