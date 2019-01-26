---
title: IDebugCoreServer3::CreateInstanceInServer | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d7d5ac21ac6f3e50dbedc141c48d30768d6fb818
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54998479"
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
Vytvoří instanci ladicího stroje na serveru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateInstanceInServer(  
   LPCWSTR  szDll,  
   WORD     wLangId,  
   REFCLSID clsidObject,  
   REFIID   riid,  
   void**   ppvObject  
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