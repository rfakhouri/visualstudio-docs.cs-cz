---
title: IDebugCoreServer3::CreateInstanceInServer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71995e38cf58c23437cbb9a6d6973fbd09cab8ab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
Vytvoří instanci modul ladění na serveru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 [v] Cesta k souboru dll, která implementuje CLSID zadaný v `clsidObject` parametr. Pokud je to `NULL`, pak COM na `CoCreateInstance` funkce je volána.  
  
 `wLangId`  
 [v] Národní prostředí ladění stroje. To může být 0, pokud [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md) neměla být volána metoda.  
  
 `clsidObject`  
 [v] CLSID modul ladění k vytvoření.  
  
 `riid`  
 [v] Rozhraní ID načíst z objektu třídy konkrétní rozhraní.  
  
 `ppvObject`  
 [out] `IUnknown` rozhraní z instancí objektu. Přetypování nebo zařazování tento objekt požadované rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [Setlocale –](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)