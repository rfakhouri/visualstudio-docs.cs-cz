---
title: IDebugProcessEx2::AddImplicitProgramNodes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords: IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: adc3f54188e57bd5453703c0aa68fe281fd2ca5e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
Tato metoda přidá program uzel pro každý motor ladění (DE) zadán.  
  
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
 [v] `GUID` Z DE, který se má použít ke spuštění programy (a předpokládá se, že přidejte vlastní program uzly).  
  
 `rgguidSpecificEngines`  
 [v] Pole `GUID`s DEs pro program, který bude přidán uzly.  
  
 `celtSpecificEngines`  
 [v] Počet `GUID`s v `rgguidSpecificEngines` pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [Programu uzly](../../../extensibility/debugger/program-nodes.md) přidá pro každý DE uvedených v `rgguidSpecificEngines`– s výjimkou spuštění modulu (jak je uveden v `guidLaunchingEngine`), který se předpokládá, že pro přidání uzlu vlastní program, když ji spustí program.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [Uzly programů](../../../extensibility/debugger/program-nodes.md)