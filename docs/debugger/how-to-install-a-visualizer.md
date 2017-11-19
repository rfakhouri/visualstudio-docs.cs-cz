---
title: "Postupy: instalace Vizualizéru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1e3bffd2a38692a9767cabbd132d4297ab1347e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-install-a-visualizer"></a>Postupy: Instalace vizualizéru
Po vytvoření vizualizéru, musíte nainstalovat vizualizér tak, že bude k dispozici v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Instalace vizualizéru je jednoduchý proces.  
  
> [!NOTE]
>  V **úložiště** aplikace, pouze standardní text, HTML, XML a JSON vizualizérech jsou podporovány. Vizualizérech vlastní (vytvořené uživatelem) nejsou podporovány.  
  
### <a name="to-install-a-visualizer"></a>Instalace vizualizéru  
  
1.  Vyhledejte knihovnu DLL, která obsahuje vizualizér, kterou jste vytvořili.  
  
2.  Kopie knihovny DLL na jednu z následujících umístění:  
  
    -   *VisualStudioInstallPath*`\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\`*VisualStudioVersion*`\Visualizers`  
  
3.  Pokud chcete použít spravované vizualizér pro vzdálené ladění, zkopírujte knihovnu DLL do stejné cesty na vzdáleném počítači.  
  
4.  Restartujte relaci ladění.  
  
## <a name="see-also"></a>Viz také  
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)   
 [Postupy: zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md)