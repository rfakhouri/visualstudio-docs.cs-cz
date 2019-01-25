---
title: Procházet úložiště k nahrávání dat.
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.service: multiple
ms.workload:
- multiple
ms.openlocfilehash: 44803eea573860074f67d2e97f1160614f452ac5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766378"
---
# <a name="browse-storage-to-upload-data-or-download-models-and-logs"></a>Procházet úložiště k ukládání dat nebo stahování modely a protokoly

Můžete procházet všechny úložiště na vzdáleném počítači nebo sdílené složky Azure k povolit nahrávání nebo stahování modely a data protokolů. Nebo, pokud chcete získat přístup, protokoly a výstupy úlohy pro konkrétní úlohu, Uděláte to i v prohlížeči projektu.

## <a name="to-access-all-data-on-the-remote-machine-or-file-share"></a>Přístup ke všem datům na vzdáleném počítači nebo sdílené položky

1. Otevřít **Průzkumníka serveru**.
2. Rozbalte vzdáleného počítače nebo služby Batch AI výpočetním kontextu.
3. Klikněte pravým tlačítkem na **úložiště**; potom klikněte na **Procházet**.

    ![úložiště](media/manage-storage/browse-storage.png)

## <a name="to-access-job-specific-data-on-the-remote-machine-or-file-share"></a>Pro přístup k datům specifické pro úlohy na vzdáleném počítači nebo sdílené položky

1. Otevřít [historie úlohy](job-details.md)
2. Vyberte úlohu.
3. Klikněte na tlačítko **pracovní složka** nebo klikněte na tlačítko **StdOut / Stderr** pro rychlý přístup k těmto souborům protokolu důležité.

    ![úložiště](media/manage-storage/job-workingfolder.png)