---
title: IDebugField::GetSize | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugField::GetSize
helpviewer_keywords:
- IDebugField::GetSize method
ms.assetid: 73329924-3751-4f44-af54-5986b7943374
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9fded9abc006ff6a28e122f0a4b8d7fae5da997b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54789200"
---
# <a name="idebugfieldgetsize"></a>IDebugField::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda načte velikost pole, v bajtech.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetSize(   
   DWORD* pdwSize  
);  
```  
  
```csharp  
int GetSize(  
   out uint pdwSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwSize`  
 [out] Vrátí velikost.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Všechna pole mít typ a všechny typy mají velikost. Pole typu byte má například velikost 1 bajt.  
  
## <a name="see-also"></a>Viz také  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
