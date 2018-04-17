---
title: Připojení po spuštění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
ms.assetid: 5a3600a1-dc20-4e55-b2a4-809736a6ae65
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 69f9f9cde76c5fa66294fd2cdbdc5252169e0183
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="attaching-after-a-launch"></a>Připojení po spuštění
Po spuštění programu relaci ladění je připraven k dané programu připojit modul ladění (DE).  
  
## <a name="design-decisions"></a>Rozhodnutí o návrhu  
 Vzhledem k tomu, že komunikace je snazší v rámci vytvořit sdílený adresní prostor, musíte se rozhodnout, zda je vhodnější usnadnění komunikace mezi relaci ladění a DE nebo mezi DE a program. Vyberte z následujících možností:  
  
-   Pokud je vhodnější pro usnadnění komunikace mezi relaci ladění a DE, relaci ladění společně vytvoří DE a požádá DE připojit k programu. Zůstane relaci ladění a DE společně v jeden adresní prostor, běhové prostředí a program společně v jiném.  
  
-   Pokud je vhodnější pro usnadnění komunikace mezi DE a program, běhové prostředí společně vytvoří DE. Zůstane SDM v jeden adresní prostor a DE, běhové prostředí a program společně v jiném. Toto je typické pro Německo, který je implementováno s překladač spustit skriptovanou jazyky.  
  
    > [!NOTE]
    >  Jak je DE připojí k programu je závislá na implementaci. Komunikace mezi DE a program je také implementace závislé.  
  
## <a name="implementation"></a>Implementace  
 Prostřednictvím kódu programu, když správce ladicí relace (SDM) nejprve obdrží [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) objektu, který představuje program, který má být spuštěn, zavolá [Attach](../../extensibility/debugger/reference/idebugprogram2-attach.md) metodu a předá ho [ IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který je novější sloužící k předávání událostí ladění zpět do SDM. `IDebugProgram2::Attach` Metoda pak zavolá [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda. Další informace o způsobu SDM obdrží `IDebugProgram2` rozhraní najdete v tématu [upozornění Port](../../extensibility/debugger/notifying-the-port.md).  
  
 Pokud vaše DE je potřeba spustit ve stejném adresním prostoru s programem laděné obvykle protože DE je součástí překladač spuštění skriptu, `IDebugProgramNodeAttach2::OnAttach` metoda vrátí `S_FALSE`, která udává, zda byla dokončena procesu připojování.  
  
 Pokud na druhé straně DE běží v adresním prostoru SDM, `IDebugProgramNodeAttach2::OnAttach` metoda vrátí `S_OK` nebo [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) rozhraní není implementováno vůbec na [IDebugProgramNode2 ](../../extensibility/debugger/reference/idebugprogramnode2.md) objekt přidružený k programu laděné. V takovém případě [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána nakonec k dokončení operace připojení.  
  
 V takovém případě musí volat [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) metodu `IDebugProgram2` objekt, který byl předán `IDebugEngine2::Attach` metoda, úložiště `GUID` v místním programu objektu a to vrátí `GUID` při `IDebugProgram2::GetProgramId` metoda je volána následně na tento objekt. `GUID` Slouží k identifikaci program jednoznačně napříč různými součástmi ladění.  
  
 Všimněte si, že u `IDebugProgramNodeAttach2::OnAttach` metoda vrací `S_FALSE`, `GUID` pro program je předaná této metodě a je `IDebugProgramNodeAttach2::OnAttach` metoda, která nastaví `GUID` na objekt místní programu.  
  
 DE je teď připojený k programu a připravené k odeslání všechny události spuštění.  
  
## <a name="see-also"></a>Viz také  
 [Připojení přímo k programu](../../extensibility/debugger/attaching-directly-to-a-program.md)   
 [Upozornění portu](../../extensibility/debugger/notifying-the-port.md)   
 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md)   
 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [Připojení](../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md)