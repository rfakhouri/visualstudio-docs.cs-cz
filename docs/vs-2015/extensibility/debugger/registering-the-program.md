---
title: Registrace programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- programs, registration
- debugging [Debugging SDK], program registration
ms.assetid: d726a161-7db3-4ef4-b258-9f6a5be68418
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 484aa854a8e0987bf034e829a3acf02d6d637870
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60042643"
---
# <a name="registering-the-program"></a>Registrace programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Po ladicí stroj získal port, reprezentovaný [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) rozhraní, je dalším krokem při povolení ladění programu registrace s portem. Po registraci do programu je k dispozici pro ladění pomocí jedné z následujících způsobů:  
  
- Proces připojení, která umožňuje ladicího programu k získání úplné kontroly ladění běžící aplikace.  
  
- Just-in-time (JIT) ladění, která umožňuje za fakt ladění programu, který se spustí bez ohledu na jejich ladicí program. Za běhu architektury zachytí chyba, ladicí program se upozornění před operačního systému nebo běhové prostředí uvolní paměť a prostředky neškodné programu.  
  
## <a name="registering-procedure"></a>Postup registrace  
  
#### <a name="to-register-your-program"></a>Registrace aplikace  
  
1. Volání [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) metoda implementovaná port.  
  
     `IDebugPortNotify2::AddProgramNode` vyžaduje ukazatel [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní.  
  
     Obvykle když operační systém nebo prostředí za běhu načte program, vytvoří uzel program. Pokud ladicí stroj (DE) se zobrazí výzva k načtení programu DE vytvoří a zaregistruje uzel programu.  
  
     Následující příklad ukazuje ladicí stroj spuštění programu a její registrací pomocí portu.  
  
    > [!NOTE]
    >  To není jediný způsob, jak spustit a pokračovat v procesu. To je především Příklad registrace programu s portem.  
  
    ```cpp#  
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
                    hr = spPortEx->LaunchSuspended(/* omitted parameters */,ppDebugProcess)  
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
 [Získání portu](../../extensibility/debugger/getting-a-port.md)   
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)
