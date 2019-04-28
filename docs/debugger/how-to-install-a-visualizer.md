---
title: 'Postupy: Instalace Vizualizéru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9b09bc837cae4eaad2c0dbcb2bb82a7daa248eb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63389324"
---
# <a name="how-to-install-a-visualizer"></a>Postupy: Instalace Vizualizéru
Po vytvoření vizualizéru, musíte nainstalovat vizualizéru tak, že bude k dispozici v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Instalace vizualizéru je jednoduchý proces.

> [!NOTE]
> V aplikacích pro UPW, pouze standardní text, HTML, XML a JSON vizualizéry jsou podporovány. Vizualizéry vlastní (uživatelem vytvořené) nejsou podporovány.

### <a name="to-install-a-visualizer"></a>Instalace vizualizéru

1. Vyhledejte knihovnu DLL, která obsahuje vizualizaci, kterou jste vytvořili.

2. Kopie knihovny DLL některou z následujících umístění:

    - *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`

    - `My Documents\` *VisualStudioVersion* `\Visualizers`

3. Pokud chcete používat spravované vizualizéru pro vzdálené ladění, zkopírujte knihovnu DLL do stejného umístění na vzdáleném počítači.

4. Restartujte relaci ladění.

## <a name="see-also"></a>Viz také
- [Vytváření vlastních vizualizérů](../debugger/create-custom-visualizers-of-data.md)
- [Postupy: Zápis vizualizéru](/visualstudio/debugger/create-custom-visualizers-of-data)