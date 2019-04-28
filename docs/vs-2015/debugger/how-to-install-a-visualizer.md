---
title: 'Postupy: Instalace Vizualizéru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5726cea8b2e81c53b5f3fff963357946f26b199f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438230"
---
# <a name="how-to-install-a-visualizer"></a>Postupy: Instalace Vizualizéru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Po vytvoření vizualizéru, musíte nainstalovat vizualizéru tak, že bude k dispozici v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Instalace vizualizéru je jednoduchý proces.  
  
> [!NOTE]
> V **Store** aplikací, jenom standardní text, HTML, XML a JSON vizualizéry jsou podporovány. Vizualizéry vlastní (uživatelem vytvořené) nejsou podporovány.  
  
### <a name="to-install-a-visualizer"></a>Instalace vizualizéru  
  
1. Vyhledejte knihovnu DLL, která obsahuje vizualizaci, kterou jste vytvořili.  
  
2. Kopie knihovny DLL některou z následujících umístění:  
  
    - *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    - `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3. Pokud chcete používat spravované vizualizéru pro vzdálené ladění, zkopírujte knihovnu DLL do stejného umístění na vzdáleném počítači.  
  
4. Restartujte relaci ladění.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních Vizualizérů](../debugger/create-custom-visualizers-of-data.md)   
 [Postupy: Zápis vizualizéru](../debugger/how-to-write-a-visualizer.md)
