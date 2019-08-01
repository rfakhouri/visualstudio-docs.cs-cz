---
title: 'Postupy: Vyloučení projektů ze sestavení'
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 54e65c411afe9815696112dfbcc99bcb9433c4db
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416862"
---
# <a name="how-to-exclude-projects-from-a-build"></a>Postupy: Vyloučení projektů ze sestavení

Můžete sestavit řešení bez nutnosti sestavovat všechny projekty, které obsahuje. Můžete například vyloučit projekt, který přerušuje sestavení. Po prozkoumání a vyřešení problémů pak můžete sestavit projekt.

Projekt můžete vyloučit provedením následujících přístupů:

- Dočasné odebrání z aktivní konfigurace řešení.

- Vytvoření konfigurace řešení, která nezahrnuje projekt.

Další informace najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).

## <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Dočasné odebrání projektu z aktivní konfigurace řešení

1. Na panelu nabídek vyberte možnost **sestavit** > **Configuration Manager**.

2. V tabulce **kontexty projektu** vyhledejte projekt, který chcete ze sestavení vyloučit.

3. Ve sloupci **sestavení** projektu zrušte zaškrtnutí políčka.

4. Klikněte na tlačítko **Zavřít** a pak znovu sestavte řešení.

## <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Vytvoření konfigurace řešení, která vylučuje projekt

1. Na panelu nabídek vyberte možnost **sestavit** > **Configuration Manager**.

2. V seznamu **aktivní konfigurace řešení** vyberte možnost  **\<nový >** .

3. Do pole **název** zadejte název pro konfiguraci řešení.

4. V seznamu **Kopírovat nastavení z** vyberte konfiguraci řešení, na které chcete založit novou konfiguraci (například **ladit**), a pak klikněte na tlačítko **OK** .

5. V dialogovém okně **Configuration Manager** zrušte zaškrtnutí políčka ve sloupci **sestavení** pro projekt, který chcete vyloučit, a poté klikněte na tlačítko **Zavřít** .

6. Na **standardním** panelu nástrojů ověřte, zda je nová konfigurace řešení aktivní konfigurace v poli **Konfigurace řešení** .

7. V panelu nabídky zvolte **sestavení** > **znovu sestavit řešení**.

## <a name="see-also"></a>Viz také:

- [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)
- [Postupy: Vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)
- [Postupy: Sestavování několika konfigurací současně](../ide/how-to-build-multiple-configurations-simultaneously.md)