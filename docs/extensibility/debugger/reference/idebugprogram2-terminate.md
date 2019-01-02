---
title: IDebugProgram2::Terminate | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c4ef57e3cbc11eb6e1b8e266d1a0799ef46ba406
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53872093"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
Ukončí program.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)