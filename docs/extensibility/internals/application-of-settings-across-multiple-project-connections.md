---
title: "Aplikace nastavení mezi více připojení projekt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a5d66bf7670d5ba9b6423461bdb5e5482819592f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Aplikace nastavení mezi více připojení projektu
Správa zdrojového kódu modulu plug-in sestaven pomocí rozhraní API 1.2 zdroj ovládacího prvku Plug-in můžete použít dávkové operace k provedení operace stejný zdroj ovládacího prvku napříč více projektů nebo kontextů více připojení. Dávky lze eliminovat redundantní, dialogová okna z činnost koncového uživatele na projekt.  
  
 Pokud uživatel vybere více položek, které patří do více než jedno připojení ve správě zdrojového kódu modulu plug-in vyvíjené Plug-in API zdroj ovládacího prvku 1.1, (například dva webové projekty na jinou sdílenou počítače) a ověří je, uživateli se zobrazí dialogové okno stejné opakovaně. K tomu dojde i v případě, že uživatel klikne **použít u všech** zaškrtněte políčko v dialogovém okně, protože rozhraní IDE obnoví stav pro každý kontext připojení.  
  
## <a name="new-capability-flag"></a>Nový příznak schopností  
 `SccBeginBatch`Funkce sady `SCC_CAP_BATCH` příznak indikující, že dávkové operace probíhá  
  
## <a name="new-functions"></a>Nové funkce  
 Následující nové funkce podporují dávkové operace:  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` Funkce spustí skupinu operace zdroj ovládacího prvku. `SccEndBatch`Zavře skupině. Nemusí být vnořené skupiny.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)