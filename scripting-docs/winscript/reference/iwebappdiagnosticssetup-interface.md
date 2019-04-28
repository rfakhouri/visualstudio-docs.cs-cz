---
title: IWebAppDiagnosticsSetup Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup Interface
ms.assetid: ec7359f2-633e-4d59-b64b-9cab0134dfd0
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71d4501fff04b62abe392c6684a4a0551dea9ee8
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443661"
---
# <a name="iwebappdiagnosticssetup-interface"></a>IWebAppDiagnosticsSetup – rozhraní
Toto rozhraní je implementováno PDM ladění aplikací k vytváření objektů COM v procesu, který je právě laděna a povolit diagnostiku web. PDM ladění aplikace objekt implementuje [IObjectWithSite](http://go.microsoft.com/fwlink/?LinkId=232438), vyžaduje aplikaci Internet Explorer [setsite –](http://go.microsoft.com/fwlink/?LinkId=232439) na ně po jejím vytvoření a předá v odkazu na [rozhraní IWebBrowser2](http://go.microsoft.com/fwlink/?LinkId=232449). Volání aplikací WWA [setsite –](http://go.microsoft.com/fwlink/?LinkId=232439) a předá v WWA rozhraní IWebApplicationHost místo. Pokud [setsite –](http://go.microsoft.com/fwlink/?LinkId=232439) setcodepage se zavolala s NENULOVOU hodnotu, [IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) vrací hodnotu true. Pokud ne, vrátí hodnotu false a volání [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) nezdaří.  
  
> [!IMPORTANT]
> `IWebAppDiagnosticsSetup` je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 Toto rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)|Získá textové dokumenty, které jsou skryty pomocí zadaného filtru.|  
|[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)|Určuje, zda zadaný dokument patří do jedné z podřízených uzlů tohoto uzlu.|