---
title: IDebugProgram2::Detach | Dokumentace Microsoftu
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
- IDebugProgram2::Detach
helpviewer_keywords:
- IDebugProgram2::Detach
ms.assetid: 5e8d88b0-a8d4-4746-88c0-ad332ee73f33
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e79cadc19dffe842a054539b5ed706f3f8b2cf1f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829115"
---
# <a name="idebugprogram2detach"></a>IDebugProgram2::Detach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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

