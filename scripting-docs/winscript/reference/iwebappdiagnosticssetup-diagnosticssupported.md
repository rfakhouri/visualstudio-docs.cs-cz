---
title: IWebAppDiagnosticsSetup::DiagnosticsSupported | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup::DiagnosticsSupported
ms.assetid: 5bbcd0d0-1460-4cf7-bbb1-f4f4a04f739a
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df9296ac251d93105229fc0af365f6797a413f2b
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349683"
---
# <a name="iwebappdiagnosticssetupdiagnosticssupported"></a>IWebAppDiagnosticsSetup::DiagnosticsSupported
Určuje, zda jsou podporovány diagnostiky pro tuto aplikaci. Pokud [setsite –](http://go.microsoft.com/fwlink/?LinkId=232439) byla volána pro objekt implementace tohoto rozhraní s NENULOVOU hodnotu, [DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) vrátí `true`. Pokud ne, vrátí `false` a volání [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) nezdaří.  
  
> [!IMPORTANT]
>  [Iwebappdiagnosticssetup – rozhraní](../../winscript/reference/iwebappdiagnosticssetup-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Součástí activdbg100.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DiagnosticsSupported(        [out, retval] VARIANT_BOOL* pRetVal        );  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 Pokud [setsite –](http://go.microsoft.com/fwlink/?LinkId=232439) byla volána pro objekt implementace tohoto rozhraní s NENULOVOU hodnotu, [DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) vrátí `true`. Pokud ne, vrátí `false`a volání [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) nezdaří.