---
title: IDebugProgram2::Terminate | Dokumentace Microsoftu
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
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e05edc99dcb408159966f08a3d38f6663f73f290
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668893"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProgram2::Terminate](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-terminate).  
  
Ukončí program.  
  
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
 Pokud je to možné bude program ukončen a byla uvolněna z procesu. v opačném případě ladicího stroje (DE) provede všechny potřebné vyčištění.  
  
 Tato metoda nebo [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) metoda je volána metodou rozhraní IDE, obvykle v reakci na zastavení ladění všechny uživatele. Implementace této metody by v ideálním případě ukončit program v rámci procesu. Pokud to není možné, DE by měl bránit spouštění všech dalších v tomto procesu programu (a proveďte všechny potřebné vyčištění). Pokud `IDebugProcess2::Terminate` byla volána metoda integrovaným vývojovým prostředím, celý proces bude ukončen nějakou dobu po `IDebugProgram2::Terminate` metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [ukončit](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)

