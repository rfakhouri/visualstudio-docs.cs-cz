---
title: IDebugField::Equal | Dokumentace Microsoftu
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
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3218b8cc61dea3d55132f5596f624108cd4d85bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628850"
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugField::Equal](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfield-equal).  
  
Tato metoda porovnává tohoto pole se zadaným polem pro rovnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```csharp  
int Equal(  
   IDebugField pField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pField`  
 [in] Pole má být porovnán s tohoto objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud pole jsou stejné, vrátí `S_OK`. Pokud pole liší, vrátí `S_FALSE.` v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

