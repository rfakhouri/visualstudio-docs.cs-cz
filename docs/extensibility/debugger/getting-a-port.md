---
title: "Získávání Port | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, getting
- debugging [Debugging SDK], ports
ms.assetid: 745c2337-cfff-4d02-b49c-3ca7c4945c5e
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5f6065c91845df020325e279a1fa3858a4f75505
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getting-a-port"></a>Získávání Port
Port představuje připojení k počítači, na kterém běží procesy. Tento počítač může být v místním počítači nebo vzdáleného počítače (který může pravděpodobně být nezaložené Windows operačním systémem, zjistit [porty](../../extensibility/debugger/ports.md) informace).  
  
 Port je reprezentována [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) rozhraní. Umožňuje získat informace o procesech spuštěných na počítači, na kterém port je připojen k.  
  
 Modul ladění potřebuje přístup k portu, chcete-li zaregistrovat program uzly port a požadavky na informace o procesu. Například, pokud modul ladění implementuje [IDebugProgramProvider2](../../extensibility/debugger/reference/idebugprogramprovider2.md) implementace pro rozhraní [GetProviderProcessData](../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) metoda může požádat port pro potřeby proces informace, které má být vrácen.  
  
 Visual Studio poskytuje nezbytné port, který se modul ladění a získá tento port od jiného dodavatele portu. Pokud program je připojena k (buď v rámci ladicího programu nebo protože došlo k výjimce došlo, která aktivuje dialogové okno těsně za běhu [JIT]), uživatel je přístup k podrobnostem o přenosu (jiný název pro dodavatele port) používat. Pokud uživatel spustí program z v ladicím programu, systému projektu, jinak hodnota Určuje dodavatele port používat. V obou případech Visual Studio vytvoří port dodavatele, reprezentována [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní a požádá o nový port voláním [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) s [ IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) rozhraní. Tento port je předána ladění modul v podobě jednoho nebo druhého.  
  
## <a name="example"></a>Příklad  
 Tento fragment kódu ukazuje, jak používat port zadaný do [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) k registraci uzlu program v [ResumeProcess](../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md). Parametry nejsou přímo související s Tento koncept pro přehlednost byly vynechány.  
  
> [!NOTE]
>  Tento příklad používá port pro spuštění a obnovte proces a předpokládá, že [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md) rozhraní je implementováno na portu. To se rozhodně není jediný způsob, jak provádět tyto úlohy a je možné, že port nemusí i zapojí jiné než a program [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) uvedené.  
  
```cpp  
// This is an IDebugEngineLaunch2 method.  
HRESULT CDebugEngine::LaunchSuspended(/* omitted parameters */,  
                                      IDebugPort2 *pPort,  
                                      /* omitted parameters */,  
                                      IDebugProcess2**ppDebugProcess)  
{  
    // do stuff here to set up for a launch (such as handling the other parameters)  
    ...  
  
    // Now get the IPortNotify2 interface so we can register a program node  
    // in CDebugEngine::ResumeProcess.  
    CComPtr<IDebugDefaultPort2> spDefaultPort;  
    HRESULT hr = pPort->QueryInterface(&spDefaultPort);  
    if (SUCCEEDED(hr))  
    {  
        CComPtr<IDebugPortNotify2> spPortNotify;  
        hr = spDefaultPort->GetPortNotify(&spPortNotify);  
        if (SUCCEEDED(hr))  
        {  
            // Remember the port notify so we can use it in ResumeProcess.  
            m_spPortNotify = spPortNotify;  
  
            // Now launch the process in a suspended state and return the  
            // IDebugProcess2 interface  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = pPort->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                // pass on the parameters we were given (omitted here)  
                hr = spPortEx->LaunchSuspended(/* omitted paramters */,ppDebugProcess)  
            }  
        }  
    }  
    return(hr);  
}  
  
HRESULT CDebugEngine::ResumeProcess(IDebugProcess2 *pDebugProcess)  
{  
    // Make a program node for this process  
    HRESULT hr;  
    CComPtr<IDebugProgramNode2> spProgramNode;  
    hr = this->GetProgramNodeForProcess(pProcess, &spProgramNode);  
    if (SUCCEEDED(hr))  
    {  
        hr = m_spPortNotify->AddProgramNode(spProgramNode);  
        if (SUCCEEDED(hr))  
        {  
            // resume execution of the process using the port given to us earlier.  
           // (Querying for the IDebugPortEx2 interface is valid here since  
           // that's how we got the IDebugPortNotify2 interface in the first place.)  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = m_spPortNotify->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                hr  = spPortEx->ResumeProcess(pDebugProcess);  
            }  
        }  
    }  
    return(hr);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Registrace do programu](../../extensibility/debugger/registering-the-program.md)   
 [Povolení Program chcete ladit](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)   
 [Port dodavatelů](../../extensibility/debugger/port-suppliers.md)   
 [Porty](../../extensibility/debugger/ports.md)