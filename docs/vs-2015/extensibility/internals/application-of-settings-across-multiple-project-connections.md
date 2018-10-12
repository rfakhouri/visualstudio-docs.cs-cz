---
title: Aplikace nastavení napříč různými připojeními projektů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 81d6a1f540314863e4e24b3b91c7f4112e0af8f0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49197610"
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Aplikace nastavení napříč různými připojeními projektů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Modul plug-in správy zdrojového kódu vytvořené pomocí rozhraní API 1.2 zdrojový ovládací prvek modulu Plug-in slouží ke spuštění stejnou operaci správy zdrojových kódů napříč více projekty nebo více kontexty připojení dávkovou operaci. Dávky je možné vyloučit redundantní, dialogová okna uživatelským prostředím jednotlivých projektů.  
  
 Pokud uživatel vybere více položek, které patří do více než jedno připojení v modulu plug-in správy zdrojového kódu, vytvořené pomocí modulu Plug-in API zdrojového ovládacího prvku 1.1, (například dvě webové projekty na počítačích jinou sdílenou složku) a ověří je, uživateli se zobrazí stejné dialogových oken opakovaně. K tomu dojde i v případě, že uživatel klikne **použít u všech** zaškrtněte políčko v dialogovém okně, protože rozhraní IDE obnoví svůj stav pro každý kontext připojení.  
  
## <a name="new-capability-flag"></a>Nový příznak funkce  
 `SccBeginBatch` Funkce sady `SCC_CAP_BATCH` příznak označující, že se probíhající operace služby batch  
  
## <a name="new-functions"></a>Nové funkce  
 Následující nové funkce podporují dávkové operace:  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` Funkce spustí skupinu operací správy zdrojů. `SccEndBatch` Zavře skupině. Skupiny nemůže být vnořený.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

