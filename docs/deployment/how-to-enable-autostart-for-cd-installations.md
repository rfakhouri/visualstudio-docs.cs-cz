---
title: 'Postupy: Povolení funkce AutoStart pro instalace z disku CD | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66f5510ae63507aebb97a7f8bdfd3e367f1afc85
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62928511"
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>Postupy: Povolení funkce AutoStart pro instalace z disku CD
Při nasazování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí vyměnitelného média jako je například disk CD-ROM nebo DVD-ROM, můžete povolit `AutoStart` tak, aby [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se automaticky spustí, když je médium je vloženo.

 `AutoStart` lze povolit **publikovat** stránku **Návrháře projektu**.

### <a name="to-enable-autostart"></a>Povolit automatické spuštění

1. S projekt vybraný v **Průzkumníka řešení**na **projektu** klikněte na nabídku **vlastnosti**.

2. Klikněte na tlačítko **publikovat** kartu.

3. Klikněte na tlačítko **možnosti** tlačítko.

     **Možnosti publikování** zobrazí se dialogové okno.

4. Klikněte na tlačítko **nasazení**.

5. Vyberte **pro instalace z CD automaticky spustit instalační program po vložení disku CD** zaškrtávací políčko.

     *Autorun.inf* soubor bude zkopírován do umístění pro publikování, když je aplikace publikována.

## <a name="see-also"></a>Viz také:
- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)