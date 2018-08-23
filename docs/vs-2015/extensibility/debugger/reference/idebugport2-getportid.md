---
title: IDebugPort2::GetPortId | Dokumentace Microsoftu
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
- IDebugPort2::GetPortId
helpviewer_keywords:
- IDebugPort2::GetPortId
ms.assetid: 837cb924-c113-4224-aa86-3e02b33dfa70
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 084fc71d3d0b502ae0ed0a6cf1ad5f6c1b421f92
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633366"
---
# <a name="idebugport2getportid"></a>IDebugPort2::GetPortId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugPort2::GetPortId](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugport2-getportid).  
  
Získá identifikátor port.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetPortId(   
   GUID* pguidPort  
);  
```  
  
```csharp  
int GetPortId(   
   out Guid pguidPort  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pguidPort`  
 [out] Vrátí identifikátor GUID, který identifikuje port.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)

