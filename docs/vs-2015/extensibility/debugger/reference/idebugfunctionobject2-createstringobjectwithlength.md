---
title: IDebugFunctionObject2::CreateStringObjectWithLength | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateStringObjectWithLength
- IDebugFunctionObject2::CreateStringObjectWithLength
ms.assetid: 1f43ec66-1615-4a4c-8b9d-e933f549f96d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 20fd1000170a662baa5770ae396da98d48e813c7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628032"
---
# <a name="idebugfunctionobject2createstringobjectwithlength"></a>IDebugFunctionObject2::CreateStringObjectWithLength
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugFunctionObject2::CreateStringObjectWithLength](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength).  
  
Vytvoří objekt string, který má zadanou délku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CreateStringObjectWithLength (  
   LPCOLESTR      pcstrString,  
   UINT           uiLength,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateStringObjectWithLength (  
   string           pcstrString,  
   uint             uiLength,  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcstrString`  
 [in] Řetězcová hodnota pro objekt řetězce.  
  
 `uiLength`  
 [in] Délka řetězce v bajtech.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt, který reprezentuje objekt nově vytvořeného řetězce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)

