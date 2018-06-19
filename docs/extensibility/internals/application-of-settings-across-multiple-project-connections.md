---
title: Aplikace nastavení mezi více připojení projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0dff30ea80fb2de9bf4d90ffa48cd2f9b3d40756
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129203"
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Aplikace nastavení mezi více připojení projektu
Správa zdrojového kódu modulu plug-in sestaven pomocí rozhraní API 1.2 zdroj ovládacího prvku Plug-in můžete použít dávkové operace k provedení operace stejný zdroj ovládacího prvku napříč více projektů nebo kontextů více připojení. Dávky lze eliminovat redundantní, dialogová okna z činnost koncového uživatele na projekt.  
  
 Pokud uživatel vybere více položek, které patří do více než jedno připojení ve správě zdrojového kódu modulu plug-in vyvíjené Plug-in API zdroj ovládacího prvku 1.1, (například dva webové projekty na jinou sdílenou počítače) a ověří je, uživateli se zobrazí dialogové okno stejné opakovaně. K tomu dojde i v případě, že uživatel klikne **použít u všech** zaškrtněte políčko v dialogovém okně, protože rozhraní IDE obnoví stav pro každý kontext připojení.  
  
## <a name="new-capability-flag"></a>Nový příznak schopností  
 `SccBeginBatch` Funkce sady `SCC_CAP_BATCH` příznak indikující, že dávkové operace probíhá  
  
## <a name="new-functions"></a>Nové funkce  
 Následující nové funkce podporují dávkové operace:  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` Funkce spustí skupinu operace zdroj ovládacího prvku. `SccEndBatch` Zavře skupině. Nemusí být vnořené skupiny.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)