---
title: IDebugProcessEx2::AddImplicitProgramNodes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f2fb2696286f1cdda32f9d9acd23717c75485f2b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53955994"
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
Tato metoda přidá program uzel pro každý ladicí stroj (DE) zadaná.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT AddImplicitProgramNodes(  
   REFGUID guidLaunchingEngine,  
   GUID*   rgguidSpecificEngines,  
   DWORD   celtSpecificEngines  
);  
```  
  
```csharp  
int AddImplicitProgramNodes(  
   ref Guid guidLaunchingEngine,  
   Guid[]   rgguidSpecificEngines,  
   uint     celtSpecificEngines  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidLaunchingEngine`  
 [in] `GUID` Z DE, který se má použít ke spuštění aplikace (a se předpokládá, že můžete přidat vlastní program uzly).  
  
 `rgguidSpecificEngines`  
 [in] Pole `GUID`s DEs pro program, který se přidá uzly.  
  
 `celtSpecificEngines`  
 [in] Počet `GUID`ve `rgguidSpecificEngines` pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [Program uzly](../../../extensibility/debugger/program-nodes.md) přidá pro každý DE uvedený v `rgguidSpecificEngines`– s výjimkou spouštění modulu (jak je uvedeno v `guidLaunchingEngine`), který předpokládá, že je přidejte vlastní program uzlu při spuštění programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [Uzly programů](../../../extensibility/debugger/program-nodes.md)