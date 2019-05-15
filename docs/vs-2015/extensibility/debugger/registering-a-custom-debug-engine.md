---
title: Registrace vlastního ladicího stroje | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9cf06e881034b980b8e40e095779007b3c7fa6f6
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65703607"
---
# <a name="registering-a-custom-debug-engine"></a>Registrace vlastního ladicího stroje
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ladicí stroj musí registrovat jako objekt pro vytváření tříd modelu COM s konvencemi také zaregistrovat pomocí sady Visual Studio prostřednictvím podklíč registru sady Visual Studio.  
  
> [!NOTE]
> Příklad toho, jak zaregistrovat ladicí stroj najdete v ukázce TextInterpreter, který je vytvořen jako součást [kurzu: Vytváření ladicího stroje pomocí knihovny ATL modelu COM](https://msdn.microsoft.com/9097b71e-1fe7-48f7-bc00-009e25940c24).  
  
## <a name="dll-server-process"></a>Proces serveru knihovny DLL  
 Obvykle ladicí stroj je implementované v jeho vlastní knihovny DLL jako COM server. To znamená, že ladicí stroj musíte zaregistrovat CLSID jeho objekt pro vytváření tříd pomocí modelu COM, před Visual Studio k němu přístup. Pak ladicí stroj musí registraci v samotné sadě Visual Studio aby bylo možné navázat žádné vlastnosti (jinak známé jako metriky) ladění modul podporuje. Výběr metriky, které jsou zapsány do sady Visual Studio podklíč registru pro ladicí stroj závisí na funkcích, které podporuje ladicího stroje.  
  
 [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) popisuje nejen umístění v registru potřeba zaregistrovat ladicí stroj; také popisuje dbgmetric.lib knihovny, který obsahuje řadu užitečných funkcí a deklarace pro vývojáře v jazyce C++, které usnadňují manipulace s jednodušší registru.  
  
### <a name="example"></a>Příklad  
 Tady je typickým příkladem (z ukázky TextInterpreter) ukazující způsob použití `SetMetric` funkce (z dbgmetric.lib), k registraci ladicího stroje pomocí sady Visual Studio. Metriky předávaný jsou také definovány v dbgmetric.lib.  
  
> [!NOTE]
> TextInterpreter je základní ladicí stroj; neimplementuje – a tedy nezaregistruje – další funkce. Úplnější ladicí stroj bude mít celý seznam `SetMetric` volání nebo ekvivalentní, jeden pro každou funkci ladicí stroj podporuje.  
  
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
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Kurz: Vytváření ladicího stroje pomocí knihovny ATL modelu COM](https://msdn.microsoft.com/9097b71e-1fe7-48f7-bc00-009e25940c24)
