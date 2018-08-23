---
title: IDebugProcess2::Terminate | Dokumentace Microsoftu
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
- IDebugProcess2::Terminate
helpviewer_keywords:
- IDebugProcess2::Terminate
ms.assetid: 5e6bf373-0fe9-4321-b04a-473a65f664d9
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a8bdecaf6b9aa0b978affdd653ba9d982f6e2002
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674486"
---
# <a name="idebugprocess2terminate"></a>IDebugProcess2::Terminate
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProcess2::Terminate](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-terminate).  
  
Ukončí proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když se proces ukončí, jsou ukončeny všechny programy v rámci tohoto procesu; žádný je, že bude možné spustit jakýkoli další kód.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

