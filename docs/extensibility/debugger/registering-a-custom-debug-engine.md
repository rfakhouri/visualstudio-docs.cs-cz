---
title: Registrace vlastního ladicího stroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3f403b18175e486dad40166d1b48960fe7b2bed2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996477"
---
# <a name="register-a-custom-debug-engine"></a>Registrace vlastního ladicího stroje
Ladicí stroj musí registrovat jako objekt pro vytváření tříd, následující konvence COM také zaregistrovat pomocí sady Visual Studio prostřednictvím podklíč registru sady Visual Studio.  
  
> [!NOTE]
>  Příklad toho, jak zaregistrovat ladicího stroje v ukázce TextInterpreter, který je vytvořen jako součást můžete najít [kurzu: Vytváření ladicího stroje pomocí knihovny ATL modelu COM](https://msdn.microsoft.com/library/9097b71e-1fe7-48f7-bc00-009e25940c24).  
  
## <a name="dll-server-process"></a>Proces serveru knihovny DLL  
 Ladicí stroj je obvykle nastavený v jeho vlastní knihovny DLL jako COM server. Ladicí stroj v důsledku toho musíte zaregistrovat CLSID jeho objekt pro vytváření tříd pomocí modelu COM před Visual Studio k němu přístup. Potom ladicí stroj musí registrovat pomocí sady Visual Studio k vytvoření libovolné vlastnosti (jinak známé jako metriky) ladění modul podporuje. Výběr metriky se zapisují do sady Visual Studio podklíč registru závisí na funkcích, které podporuje ladicí stroj.  
  
 [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) popisuje nejen umístění v registru potřeba zaregistrovat ladicí stroj; také popisuje *dbgmetric.lib* knihovny, která obsahuje mnoho užitečných funkcí a deklarace pro vývojáře v jazyce C++, které usnadňují manipulace s jednodušší registru.  
  
### <a name="example"></a>Příklad  
 Následující příklad (z ukázky TextInterpreter) ukazuje způsob použití `SetMetric` – funkce (z *dbgmetric.lib*), k registraci ladicího stroje pomocí sady Visual Studio. Metriky předávaný jsou také definovány v *dbgmetric.lib*.  
  
> [!NOTE]
>  TextInterpreter je základní ladicí stroj; nejsou nastaveny – a tedy nezaregistruje – další funkce. Úplnější ladicí stroj bude mít celý seznam `SetMetric` volání nebo ekvivalentní, jeden pro každou funkci ladicí stroj podporuje.  
  
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
  
## <a name="see-also"></a>Viz také:  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Kurz: Vytváření ladicího stroje pomocí knihovny ATL modelu COM](https://msdn.microsoft.com/library/9097b71e-1fe7-48f7-bc00-009e25940c24)