---
ms.technology: vs-ai-tools
ms.openlocfilehash: f11a66fd06a2b0b3b23d35c3153c5dd26fab282e
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="view-recent-job-performance-and-details"></a>Zobrazit nejnovější úlohy výkon a podrobnosti
Po odeslání úlohy se zobrazí se seznam úloh, které chcete zobrazit jejich stav, doba trvání a další.

1. V **Průzkumníka serveru** rozbalte konkrétní výpočetní kontextu
1. Klikněte dvakrát na **úlohy**
1. Zobrazí se seznam úlohy, odeslané do tohoto kontextu výpočty.
1. Vyberte konkrétní **úlohy** v seznamu zobrazíte podrobnosti

![Sledování úloh](media\job-details\monitor-jobs.png)

> Historie úlohy, odeslané na virtuální počítače s Linuxem jsou uloženy na virtuální počítač v adresáři TMP. Proto vždy, když se po restartu je zrušeno historie úlohy. Pro trvalé záznam historii úlohy nakonfigurujte virtuální počítač jako kontext výpočty v Azure Machine learning, pak odeslat úlohu Azure Machine Learning (výběru virtuálního počítače jako kontext výpočetní)