---
title: IDebugCoreServer3::CreateInstanceInServer | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8536fe85e58d3c43784d52b85d50015225068141
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674861"
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugCoreServer3::CreateInstanceInServer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver).  
  
Vytvoří instanci ladicího stroje na serveru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CreateInstanceInServer(  
   LPCWSTR  szDll,  
   WORD     wLangId,  
   REFCLSID clsidObject,  
   REFIID   riid,  
   void**   ppvObject  
);  
```  
  
```csharp  
int CreateInstanceInServer(  
   string     szDll,   
   ushort     wLangID,   
   ref Guid   clsidObject,   
   ref Guid   riid,   
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szDll`  
 [in] Cesta k souboru dll, která implementuje identifikátor CLSID určený v `clsidObject` parametru. Pokud je to `NULL`, pak modelu COM `CoCreateInstance` funkce je volána.  
  
 `wLangId`  
 [in] Národní prostředí ladicího stroje. To může být 0, pokud [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md) by neměla být volána metoda.  
  
 `clsidObject`  
 [in] Identifikátor CLSID ladicího stroje vytvořit.  
  
 `riid`  
 [in] Rozhraní ID pro načtení z objektu třídy konkrétní rozhraní.  
  
 `ppvObject`  
 [out] `IUnknown` rozhraní z instance objektu. Přetypování nebo přeuspořádat tento objekt na požadované rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)

