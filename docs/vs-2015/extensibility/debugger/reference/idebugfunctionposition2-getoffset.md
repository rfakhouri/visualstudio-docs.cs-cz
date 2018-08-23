---
title: IDebugFunctionPosition2::GetOffset | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugFunctionPosition2::GetOffset
helpviewer_keywords:
- IDebugFunctionPosition2::GetOffset
ms.assetid: 60943782-aec7-4be2-b222-1984ed53a543
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3cdfcaa8302d2c9d72ad0d0156a07a06f9e4bdf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675077"
---
# <a name="idebugfunctionposition2getoffset"></a>IDebugFunctionPosition2::GetOffset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugFunctionPosition2::GetOffset](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionposition2-getoffset).  
  
Načte pozici funkce ve zdrojovém dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetOffset(   
   TEXT_POSITION* pPosition  
);  
```  
  
```csharp  
int GetOffset(  
   TEXT_POSITION[] pPosition  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pPosition`  
 [out v] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která se vyplní umístění funkce v dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)

