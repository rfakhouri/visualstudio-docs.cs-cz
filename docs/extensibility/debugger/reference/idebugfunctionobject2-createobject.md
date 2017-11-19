---
title: IDebugFunctionObject2::CreateObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugFunctionObject2::CreateObject
- CreateObject
ms.assetid: 148de615-941e-4b64-ab11-75b692aae465
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 08ae477758aabb2b65b5823a37a9c07d61d4083b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugfunctionobject2createobject"></a>IDebugFunctionObject2::CreateObject
Vytvoří objekt, který používá konstruktor daného nastavení příznaku vyhodnocení a hodnotu časového limitu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateObject (  
   IDebugFunctionObject* pConstructor,  
   DWORD                 dwArgs,  
   IDebugObject*         pArgs[],  
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugObject**        ppObject  
);  
```  
  
```csharp  
int CreateObject (  
   IDebugFunctionObject pConstructor,  
   uint                 dwArgs,  
   IDebugObject[]       pArgs,  
   uint                 dwEvalFlags,  
   uint                 dwTimeout,  
   out IDebugObject**   ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pConstructor`  
 [v] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt, který reprezentuje konstruktoru objektu, který se má vytvořit.  
  
 `dwArgs`  
 [v] Počet parametrů `pArg` pole. Představuje počet parametrů předaný konstruktoru.  
  
 `pArgs`  
 [v] Pole [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty, které představuje parametry předaný konstruktoru.  
  
 `dwEvalFlags`  
 [v] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet, který určit, jak má provést vyhodnocení.  
  
 `dwTimeout`  
 [v] Maximální doba v milisekundách pro čekání před návratem od této metody. Použití **NEKONEČNÉ** čekání po neomezenou dobu.  
  
 `ppObject`  
 [out] Vrátí **IDebugObject** představující nově vytvořený objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volejte tuto metodu pro vytvoření objektu, který představuje instanci třídy nebo jiné komplexní typ, který vyžaduje konstruktor, který je parametr.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)