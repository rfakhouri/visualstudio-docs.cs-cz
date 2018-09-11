---
ms.technology: vs-ai-tools
ms.openlocfilehash: d52ed79b28794a3bc1532822e0eb75b6277314b2
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44280698"
---
# <a name="browse-storage-to-upload-data-or-download-models-and-logs"></a>Procházet úložiště k ukládání dat nebo stahování modely a protokoly

Můžete procházet všechny úložiště na vzdáleném počítači nebo sdílené složky Azure k povolit nahrávání nebo stahování modely a data protokolů. Nebo, pokud chcete získat přístup, protokoly a výstupy úlohy pro konkrétní úlohu, Uděláte to i v prohlížeči projektu.

## <a name="to-access-all-data-on-the-remote-machine-or-file-share"></a>Přístup ke všem datům na vzdáleném počítači nebo sdílené položky
1. Otevřít **Průzkumníka serveru**.
2. Rozbalte vzdáleného počítače nebo služby Batch AI výpočetním kontextu.
3. Klikněte pravým tlačítkem na **úložiště**; potom klikněte na **Procházet**.

    ![úložiště](media\manage-storage\browse-storage.png)

## <a name="to-access-job-specific-data-on-the-remote-machine-or-file-share"></a>Pro přístup k datům specifické pro úlohy na vzdáleném počítači nebo sdílené položky
1. Otevřít [historie úlohy](job-details.md)
2. Vyberte úlohu.
3. Klikněte na tlačítko **pracovní složka** nebo klikněte na tlačítko **StdOut / Stderr** pro rychlý přístup k těmto souborům protokolu důležité.

    ![úložiště](media\manage-storage\job-workingfolder.png)
