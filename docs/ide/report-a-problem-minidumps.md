---
title: Vytvoření mini výpisy se všechny zásobníky volání
ms.date: 06/27/2019
ms.topic: conceptual
helpviewer_keywords:
- minidumps for Visual Studio issues"
author: mikeblome
ms.author: mblome
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Collect minidumps to send to Microsoft for help with troubleshooting issues with Visual Studio
ms.openlocfilehash: eefcbefa8b728afa677e7bd04fd538633ae117f0
ms.sourcegitcommit: 6f7a740750b2cd17ea2275c3d046caebc9782917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67518232"
---
# <a name="create-minidumps-for-a-visual-studio-process-with-all-call-stacks"></a>Vytvoření mini výpisy pro proces sady Visual Studio se všechny zásobníky volání

V některých případech může Microsoft požádat o minimální výpis spuštěných procesů pro Visual Studio spolu s informacemi o všech zásobnících volání. Tyto informace můžete shromáždit, proveďte tyto kroky:

## <a name="create-the-minidump-file"></a>Vytvořte soubor s minimálním výpisem

1. Spusťte novou instanci sady Visual Studio.
1. V hlavní nabídce zvolte **ladění** > **připojit k procesu**.
1. Zkontrolujte příslušné **spravované** a **nativní** zaškrtávací políčka a stiskněte klávesu **připojit**.

   ![Připojení k procesu](../ide/media/attach-to-process.png)

1. Vyberte jiné instanci aplikace Visual Studio k připojení ze seznamu spuštěných procesů.
1. V hlavní nabídce zvolte **ladění** > **příkaz Pozastavit vše**.
1. V hlavní nabídce zvolte **ladění** > **uložit výpis paměti jako**.

## <a name="get-the-call-stacks-from-the-minidump"></a>Získat zásobníky volání v minimálním výpisu

1. V sadě Visual Studio otevřete soubor s výpisem paměti.

1. Máte k **nástroje** > **možnosti** > **ladění** > **symboly** a ujistěte se, že  **Microsoft Symbol Servers** se změnami **Symbol umístění souborů (.pdb)** .
1. Otevřít **příkaz** okno (**zobrazení** > **ostatní Windows** > **příkazové okno**)
1. Typ ' ~ * k ". V okně zobrazí všechna vlákna zásobníky volání.
1. Kopírovat všechen text z příkazové okno a uložte do textového souboru.
1. Připojení souboru txt k chybě.
