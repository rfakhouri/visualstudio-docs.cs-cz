---
title: IWebAppDiagnosticsObjectInitialization Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: c892d3eceea65f16c69bfd2202b1f64181773532
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348045"
---
# <a name="iwebappdiagnosticsobjectinitialization-interface"></a>IWebAppDiagnosticsObjectInitialization – rozhraní
Toto rozhraní je možné implementovat na třídy, které implementují [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md). [Iwebappdiagnosticssetup – rozhraní](../../winscript/reference/iwebappdiagnosticssetup-interface.md) je implementováno prostřednictvím objektu, který implementuje [idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md). Ve většině případů se tento objekt PDM.  
  
 Po vytvoření objektu [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) je volána s odkazem na aplikaci PDM ladění a `hPassToObject` parametr `CreateObjectWithSiteAtWebApp`.  
  
> [!IMPORTANT]
>  `IWebAppDiagnosticsObjectInitialization` najdete v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 Toto rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md)|Inicializuje objekt.|