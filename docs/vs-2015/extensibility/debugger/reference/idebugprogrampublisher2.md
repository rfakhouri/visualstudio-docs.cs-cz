---
title: IDebugProgramPublisher2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramPublisher2
helpviewer_keywords:
- IDebugProgramPublisher2 interface
ms.assetid: b1d17f63-7146-4076-a588-034cfc6858b9
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3cad86071904b2af4c22a2cb1a0ef67d7de95d84
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62431456"
---
# <a name="idebugprogrampublisher2"></a>IDebugProgramPublisher2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní podporuje ladicí stroj (DE) nebo vlastní port dodavatelů k registraci programy pro ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramPublisher2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní zaregistrovat programy, který se právě ladí, aby bylo možné je zpřístupněte pro ladění napříč více procesy.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání modelu COM `CoCreateInstance` s funkcí `CLSID_ProgramPublisher` získat toto rozhraní (podívejte se na příklad). Zavedenými nebo dodavatele port. Tento vlastní port používá toto rozhraní zaregistrovat uzly programů, které představují programy, které jsou právě laděny.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)|Zpřístupní uzlu program DEs a relace ladění správci.|  
|[UnpublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogramnode.md)|Odebere program uzlu tak, aby již není k dispozici.|  
|[PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)|Zpřístupní program DEs a SDM.|  
|[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)|Odebere program, takže už nejsou k dispozici.|  
|[SetDebuggerPresent](../../../extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent.md)|Nastaví příznak označující, zda ladicí program je k dispozici.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní umožňuje programy a uzly programů k dispozici (tedy "publikují") pro algoritmus DEs a správce ladění relace (SDM). Chcete-li získat přístup k publikované programy a uzly programů, použijte [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) rozhraní. Toto je jediný způsob, jakým Visual Studio dokáže rozpoznat, že je program laděn.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak vytvořit instanci vydavatele aplikace a registrovat uzel programu. To je převzata z kurzu [publikování uzlu Program](http://msdn.microsoft.com/d0100e02-4e2b-4e72-9e90-f7bc11777bae).  
  
```cpp#  
// This is how m_srpProgramPublisher is defined in the class definition:  
// CComPtr<IDebugProgramPublisher2> m_srpProgramPublisher.  
  
void CProgram::Start(IDebugEngine2 * pEngine)  
{  
    m_spEngine = pEngine;  
  
    HRESULT hr = m_srpProgramPublisher.CoCreateInstance(CLSID_ProgramPublisher);  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to create the program publisher: 0x%x.", hr);  
        return;  
    }  
  
    // Register ourselves with the program publisher. Note that  
    // CProgram implements the IDebgProgramNode2 interface, hence  
    // the static cast on "this".  
    hr = m_srpProgramPublisher->PublishProgramNode(  
        static_cast<IDebugProgramNode2*>(this));  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to publish the program node: 0x%x.", hr);  
        m_srpProgramPublisher.Release();  
        return;  
    }  
  
    ATLTRACE("Added program node.\n");  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)
