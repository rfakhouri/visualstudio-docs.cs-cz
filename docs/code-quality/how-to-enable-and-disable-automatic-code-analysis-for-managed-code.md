---
title: 'Postupy: povolení a zákaz automatické analýzy kódu pro spravovaný kód | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2420fa388227153f3a3914c87ca1992316d06ce0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Postupy: povolení a zákaz automatické analýzy kódu pro spravovaný kód

Analýza kódu má spustit po každé sestavení spravovaný projekt kódu můžete nakonfigurovat. Vlastnosti analýzy pro každou konfiguraci sestavení můžete nastavit jiný kód.

## <a name="to-enable-or-disable-automatic-code-analysis"></a>K povolení nebo zákaz automatické analýzy kódu

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a potom vyberte **vlastnosti**.

1. V dialogovém okně Vlastnosti projektu zvolte **analýza kódu**.

1. Zadejte typ sestavení v **konfigurace** a cílová platforma v **platformy**.

1. Pokud chcete povolit nebo zakázat automatické analýzy kódu, zaškrtněte nebo zrušte **povolit analýza kódu při sestavování** zaškrtávací políčko.
