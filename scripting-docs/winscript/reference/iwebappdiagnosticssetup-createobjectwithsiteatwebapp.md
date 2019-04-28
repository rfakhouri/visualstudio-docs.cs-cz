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
ms.openlocfilehash: 42f92cfe9245a5e3a6342c31fc996ae2db50ef70
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443697"
---
# <a name="iwebappdiagnosticssetupcreateobjectwithsiteatwebapp"></a>IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
Tato metoda vytvoří společně třídy, jejíž ID předáte pomocí `rclsid` pomocí `dwClsContext`. Toto je podobným způsobem, jakým [IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md) funguje, s výjimkou, že v případě třídy `CreateObjectWithSiteAtWebApp` objekt je vytvořen asynchronně na vlákně UI webové aplikace. Objekt určený pomocí ID třídy by měly implementovat [iwebappdiagnosticsobjectinitialization – rozhraní](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md). Po vytvoření objektu [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) je volána s odkazem na aplikaci PDM ladění a `hPassToObject` parametr `CreateObjectWithSiteAtWebApp`. Tuto metodu můžete použít k předání do aplikace popisovač nepojmenovaného kanálu, kterou jste zkopírovali pomocí [DuplicateHandle](http://go.microsoft.com/fwlink/?LinkId=232450).  
  
> [!IMPORTANT]
> [Iwebappdiagnosticssetup – rozhraní](../../winscript/reference/iwebappdiagnosticssetup-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
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