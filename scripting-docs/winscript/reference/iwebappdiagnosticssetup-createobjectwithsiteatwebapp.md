---
title: IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
ms.assetid: 30975973-acb1-48f4-8266-5e097a57db22
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 26403a168268e817644637544d64d4205c398b75
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157656"
---
# <a name="iwebappdiagnosticssetupcreateobjectwithsiteatwebapp"></a>IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
Tato metoda vytvoří společně třídy, jejíž ID předáte pomocí `rclsid` pomocí `dwClsContext`. Toto je podobným způsobem, jakým [IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md) funguje, s výjimkou, že v případě třídy `CreateObjectWithSiteAtWebApp` objekt je vytvořen asynchronně na vlákně UI webové aplikace. Objekt určený pomocí ID třídy by měly implementovat [iwebappdiagnosticsobjectinitialization – rozhraní](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md). Po vytvoření objektu [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) je volána s odkazem na aplikaci PDM ladění a `hPassToObject` parametr `CreateObjectWithSiteAtWebApp`. Tuto metodu můžete použít k předání do aplikace popisovač nepojmenovaného kanálu, kterou jste zkopírovali pomocí [DuplicateHandle](http://go.microsoft.com/fwlink/?LinkId=232450).  
  
> [!IMPORTANT]
>  [Iwebappdiagnosticssetup – rozhraní](../../winscript/reference/iwebappdiagnosticssetup-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateObjectWithSiteAtWebApp(        [in] REFCLSID rclsid,         [in] DWORD dwClsContext,         [in] REFIID riid,         [in] DWORD_PTR hPassToObject        );  
```  
  
#### <a name="parameters"></a>Parametry  
 `rclsid`  
 ID třídy k vytvoření třídy.  
  
 `dwClsContext`  
 Kontext, ve kterém se spustí kód. Ve většině případů je CLSCTX_INPROC_SERVER.  
  
 `riid`  
 Nepoužívá se.  
  
 `hPassToObject`  
 Hodnota, která se předají do objektu Jakmile je vytvořen na vlákně uživatelského rozhraní, pokud objekt implementuje [iwebappdiagnosticsobjectinitialization – rozhraní](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md).