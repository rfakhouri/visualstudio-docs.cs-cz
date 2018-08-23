---
title: IDebugProgram2::Detach | Dokumentace Microsoftu
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
- IDebugProgram2::Detach
helpviewer_keywords:
- IDebugProgram2::Detach
ms.assetid: 5e8d88b0-a8d4-4746-88c0-ad332ee73f33
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 610b96c22e1fa64a0434b0b8bbdaeec506373135
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672683"
---
# <a name="idebugprogram2detach"></a>IDebugProgram2::Detach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProgram2::Detach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-detach).  
  
Odpojí ladicí stroj z programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Detach(   
   void   
);  
```  
  
```csharp  
int Detach();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Odpojit program bude nadále spuštěn, ale je již součástí relace ladění. Žádné další události ladicí program se posílají až odpojit ladicí stroj.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

