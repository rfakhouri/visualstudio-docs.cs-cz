---
title: IDebugArrayField::GetRank | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4fee642bb5f19efb62b631d71d3ba95eec45c0be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099906"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
Získá pořadí nebo počet rozměrů pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwRank`  
 [out] Vrátí pořadí.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pořadí pole odpovídá počet dimenzí. V jazyce C++ a C# vícerozměrných polí jsou skutečně pole polí a lze proto považovat za právě jednorozměrné pole (a `GetRank` metoda vždy vrátí hodnotu 1). V [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], na druhé straně vícerozměrných polí jsou zpracovány jinak a počet dimenzí odráží pořadí takové pole (a `GetRank` metoda vždy vrátí počet dimenzí).  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)