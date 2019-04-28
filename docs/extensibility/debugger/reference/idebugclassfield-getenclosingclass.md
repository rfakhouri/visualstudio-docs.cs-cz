---
title: IDebugClassField::GetEnclosingClass | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9e6b2cfae694d0d95f70b2251efc66764df1b539
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922775"
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
