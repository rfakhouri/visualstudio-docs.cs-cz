---
title: IDebugEngine2::CreatePendingBreakpoint | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2::CreatePendingBreakpoint
helpviewer_keywords:
- IDebugEngine2::CreatePendingBreakpoint
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 84c36d08c7ad907006eb9f41d2f6e2c9cd77e7bf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68196035"
---
# <a name="idebugengine2creatependingbreakpoint"></a>IDebugEngine2::CreatePendingBreakpoint
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vytvoří čekající zarážka v ladicí stroj (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CreatePendingBreakpoint(   
   IDebugBreakpointRequest2*  pBPRequest,  
   IDebugPendingBreakpoint2** ppPendingBP  
);  
```  
  
```csharp  
int CreatePendingBreakpoint(   
   IDebugBreakpointRequest2     pBPRequest,  
   out IDebugPendingBreakpoint2 ppPendingBP  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pBPRequest`  
 [in] [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) objekt, který popisuje čekající zarážka k vytvoření.  
  
 `ppPendingBP`  
 [out] Vrátí [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) objekt, který reprezentuje čekající zarážka.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Obvykle vrací `E_FAIL` Pokud `pBPRequest` parametru se neshoduje s libovolný jazyk podporuje DE if `pBPRequest` parametru je neplatná nebo neúplná.  
  
## <a name="remarks"></a>Poznámky  
 Čekající zarážkou je v podstatě kolekce všechny informace potřebné k vytvoření vazby zarážku do kódu. Čekající zarážka vrácené z této metody není vázán na kód, dokud [svázat](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) metoda je volána.  
  
 Pro každou čekající zarážka nastaví uživatele, Správce ladění relace (SDM) volá tuto metodu v každé připojené DE. Je až za ověření, že je platný pro programy spuštěné v této DE zarážku.  
  
 Pokud uživatel nastaví zarážku na řádek kódu, DE je bezplatné navázat zarážku na nejbližší řádek v dokumentu, který odpovídá tento kód. To umožňuje uživateli nastavit zarážku na první řádek příkazu více řádků, ale vytvořte jeho vazbu na posledním řádku (kde veškerý kód atributem v ladicích informací).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CProgram` objektu. Implementace je DE `IDebugEngine2::CreatePendingBreakpoint` může potom je předejte všechna volání této implementaci metody v každém programu.  
  
```  
HRESULT CProgram::CreatePendingBreakpoint(IDebugBreakpointRequest2* pBPRequest, IDebugPendingBreakpoint2** ppPendingBP)     
{    
  
   // Create and initialize the CPendingBreakpoint object.  
   CComObject<CPendingBreakpoint> *pPending;    
   CComObject<CPendingBreakpoint>::CreateInstance(&pPending);    
   pPending->Initialize(pBPRequest, m_pInterp, m_pCallback, m_pEngine);    
   return pPending->QueryInterface(ppPendingBP);    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [Vytvoření vazby](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
