---
title: Registrace do programu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- programs, registration
- debugging [Debugging SDK], program registration
ms.assetid: d726a161-7db3-4ef4-b258-9f6a5be68418
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: febc798888cc046e514db4013edb077e25f5aaca
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126298"
---
# <a name="registering-the-program"></a>Registrace do programu
Po modul ladění získal port, reprezentována [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) rozhraní, je dalším krokem při povolování program, který chcete ladit a zaregistrujte ho pomocí portu. Po registraci programu je k dispozici pro ladění pomocí jedné z těchto způsobů:  
  
-   Proces připojení, který umožňuje získat ladění kontrolu spuštěné aplikace ladicího programu.  
  
-   V běhu (JIT) ladění, která umožňuje za fakt ladění programu, který spouští nezávisle na ladicí program. Při běhu architektura zachytí chybu, ladicího programu upozornění před operačního systému nebo prostředí runtime uvolní paměť a prostředky chybující programu.  
  
## <a name="registering-procedure"></a>Postup registrace  
  
#### <a name="to-register-your-program"></a>K registraci vašeho programu  
  
1.  Volání [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) metoda implementované port.  
  
     `IDebugPortNotify2::AddProgramNode` ukazatel na vyžaduje [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní.  
  
     Obvykle když operační systém nebo běhové prostředí načte program, vytvoří uzlu programu. Pokud modul ladění (DE) se zobrazí výzva k načtení program DE vytvoří a zaregistruje uzlu programu.  
  
     Následující příklad ukazuje modul ladění spuštěním programu a její registrací s portem.  
  
    > [!NOTE]
    >  Toto není jediný způsob, jak spustit a pokračovat v procesu; Toto je především Příklad registrace program s portem.  
  
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
 [Získávání Port](../../extensibility/debugger/getting-a-port.md)   
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)