---
title: IWebAppDiagnosticsObjectInitialization Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsObjectInitialization Interface
ms.assetid: 32847838-01d9-4205-a811-3043d8c7a917
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a992f8512d4927eeb58d6437ccb830abda688b28
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443684"
---
# <a name="iwebappdiagnosticsobjectinitialization-interface"></a>IWebAppDiagnosticsObjectInitialization – rozhraní
Toto rozhraní je možné implementovat na třídy, které implementují [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md). [Iwebappdiagnosticssetup – rozhraní](../../winscript/reference/iwebappdiagnosticssetup-interface.md) je implementováno prostřednictvím objektu, který implementuje [idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md). Ve většině případů se tento objekt PDM.  
  
 Po vytvoření objektu [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) je volána s odkazem na aplikaci PDM ladění a `hPassToObject` parametr `CreateObjectWithSiteAtWebApp`.  
  
> [!IMPORTANT]
> `IWebAppDiagnosticsObjectInitialization` najdete v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 Toto rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md)|Inicializuje objekt.|