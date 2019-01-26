---
title: IDebugClassField::GetDefaultIndexer | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::GetDefaultIndexer
helpviewer_keywords:
- IDebugClassField::GetDefaultIndexer method
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 90d2b89d8e687077c490f6157b5eda53b46e97c8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961007"
---
# <a name="idebugclassfieldgetdefaultindexer"></a>IDebugClassField::GetDefaultIndexer
Získá název výchozímu indexeru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDefaultIndexer(   
   BSTR* pbstrIndexer  
);  
```  
  
```csharp  
int GetDefaultIndexer(  
   out string pbstrIndexer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrIndexer`  
 [out] Vrátí řetězec obsahující název výchozí indexeru.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistuje žádný výchozí indexer. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Indexer výchozí třídy je vlastnost, která je označena jako `Default` vlastnost pro pole přístupy. To je specifické pro [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]. Tady je příklad výchozímu indexeru deklarované v [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] a způsobu jejich použití.  
  
```vb  
Imports System.Collections;  
  
Public Class Class1  
    Private myList as Hashtable  
  
    Default Public Property Item(ByVal Index As Integer) As Integer  
        Get  
            Return CType(List(Index), Integer)  
        End Get  
        Set(ByVal Value As Integer)  
            List(Index) = Value  
        End Set  
    End Property  
End Class  
  
Function GetItem(Index as Integer) as Integer  
    Dim classList as Class1 = new Class1  
    Dim value as Integer  
  
    ' Access array through default indexer  
    value = classList(2)  
  
    ' Access array through explicit property  
    value = classList.Item(2)  
  
    Return value  
End Function  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)