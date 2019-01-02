---
title: IDebugDocumentText2::GetSize | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ee62052911ab724fd220c7a808022c5f35b49f74
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859916"
---
# <a name="idebugdocumenttext2getsize"></a>IDebugDocumentText2::GetSize
Získá velikost textu na této pozici v dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetSize(   
   ULONG* pcNumLines,  
   ULONG* pcNumChars  
);  
```  
  
```csharp  
int GetSize(   
   ref uint pcNumLines,  
   ref uint pcNumChars  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcNumLines`  
 [out] Vrátí počet řádků textu.  
  
 `pcNumChars`  
 [out] Vrátí počet znaků textu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [Jenom C++] Pokud konkrétní hodnoty není žádoucí, předejte hodnotu NULL pro parametr.  
  
 [C# pouze] Je třeba zadat oba parametry.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)