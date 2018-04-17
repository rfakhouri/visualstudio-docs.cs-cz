---
title: Vlastní registrace ladění modul | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 99ff41f116e569baaae312acd17408928a6c79f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="registering-a-custom-debug-engine"></a>Registrace modulu vlastní ladění
Modul ladění musí registrovat jako objekt pro vytváření tříd souladu s konvencemi prostředí COM a také zaregistrovat pomocí sady Visual Studio prostřednictvím podklíč registru Visual Studio.  
  
> [!NOTE]
>  Příklad toho, jak zaregistrovat modul ladění naleznete v ukázce TextInterpreter, která je integrována jako součást [kurz: vytvoření ladění modulu pomocí knihovny ATL COM](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24).  
  
## <a name="dll-server-process"></a>Proces serveru knihovny DLL  
 Obvykle je modul ladění implementovaný v jeho vlastní knihovny DLL jako COM server. To znamená, že modul ladění musí zaregistrovat CLSID jeho třída objektu pro vytváření u modelu COM, než Visual Studio k němu přístup. Potom modul ladění musí se registrovat pomocí sady Visual Studio, samotné aby bylo možné navázat žádné vlastnosti (jinak se označuje jako metriky) ladění modul podporuje. Volba metriky, které se zapisují do podklíče registru Visual Studio pro modul ladění závisí na funkce, které podporuje modul ladění.  
  
 [Pomocníci SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) popisuje nejen v umístění registru potřebné k registraci modul ladění; také popisuje dbgmetric.lib knihovny, který obsahuje počet užitečné funkce a deklarace pro vývojáře C++, které manipulace s registru jednodušší.  
  
### <a name="example"></a>Příklad  
 Následuje typický příklad (z ukázka TextInterpreter) ukazující způsob použití `SetMetric` funkci (z dbgmetric.lib), aby se zaregistrovat modul ladění pomocí sady Visual Studio. Metriky předávány je definována v dbgmetric.lib.  
  
> [!NOTE]
>  TextInterpreter je modul základní ladění; neimplementuje – a proto nezaregistruje – další funkce. Modul obsáhlejší ladění by měla mít celý seznam `SetMetric` volání nebo ekvivalenty, jeden pro každou funkci ladění modul podporuje.  
  
```  
// Define base registry subkey to Visual Studio.  
static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0";  
  
HRESULT CTextInterpreterModule::RegisterServer(BOOL bRegTypeLib, const CLSID * pCLSID)  
{  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricName, L"Text File", false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricCLSID, CLSID_Engine, false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricProgramProvider, CLSID_MsProgramProvider, false, strRegistrationRoot);  
  
    return base::RegisterServer(bRegTypeLib, pCLSID);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních ladění modulu](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [Pomocníci SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Kurz: Vytvoření modul ladění pomocí knihovny ATL COM](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)