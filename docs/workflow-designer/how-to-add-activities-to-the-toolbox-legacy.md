---
title: 'Návrhář postupu provádění - postupy: přidání aktivit do sady nástrojů (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- Toolbox, adding activities
- activities, adding to Toolbox
ms.assetid: b66ea29c-120b-40ba-8a61-c1c8240850fa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 99a8e1cef2ff5ddd526133355c608fa5218573d1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-activities-to-the-toolbox-legacy"></a>Postupy: přidání aktivit do sady nástrojů (zastaralé)

Při vytváření řešení pracovního postupu pomocí starší verze návrháře pracovních postupů Windows, která cílí rozhraní .NET Framework verze 3.5 nebo WinFX, vlastní aktivity mohou být přidány do projektu pracovního postupu a jejich designeru uložena v umístění **sada nástrojů** pro snadný přístup. Můžete také přidat aktivity přímo na **sada nástrojů** z dynamická knihovna (DLL).

## <a name="to-add-an-activity-to-the-toolbox-from-a-dll"></a>Chcete-li přidat aktivity do sady nástrojů z knihovny DLL

1.  Klikněte pravým tlačítkem na ploše okno sady nástrojů za **Windows Workflow**a potom klikněte na **zvolit položky**.

2.  V **výběr položek sady nástrojů** dialogové okno, klikněte na tlačítko **systém. součásti** a pak klikněte **Procházet** z pravé straně dolní části okna.

3.  Vyberte knihovnu DLL z adresáře soubor, který obsahuje implementaci vlastní aktivity pro přidání do **sada nástrojů**a potom klikněte na **otevřete**.

4.  Klikněte na tlačítko **OK** dokončíte přidání aktivity do sady nástrojů.

## <a name="see-also"></a>Viz také

- [Používání starší verze návrháře aktivit](../workflow-designer/using-the-legacy-activity-designer.md)
- [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)