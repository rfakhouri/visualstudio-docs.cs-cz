---
title: IDebugCoreServer3::CreateInstanceInServer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords: IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cbd287f5ab75374a3272ecbb34c36ffdf384ba84
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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