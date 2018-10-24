---
title: IDebugPortEx2::GetProgram | Dokumentace Microsoftu
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
- IDebugPortEx2::GetProgram
helpviewer_keywords:
- IDebugPortEx2::GetProgram
ms.assetid: cd83a111-bfd5-4eae-b576-526466c6b6ec
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f72184f907d57620a4597671291e25da6cf084f6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49840152"
---
# <a name="idebugportex2getprogram"></a>IDebugPortEx2::GetProgram
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá program přidružený k uzlu programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetProgram(   
   IDebugProgramNode2* pProgramNode,  
   IDebugProgram2**    ppProgram  
);  
```  
  
```csharp  
int GetProgram(   
   IDebugProgramNode2 pProgramNode,  
   out IDebugProgram2 ppProgram  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProgramNode`  
 [in] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekt představující uzel programu.  
  
 `ppProgram`  
 [out] Vrátí [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje program přidružený k uzlu programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

