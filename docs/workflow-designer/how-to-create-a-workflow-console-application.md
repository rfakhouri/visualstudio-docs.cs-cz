---
title: 'Návrhář postupu provádění - postupy: vytvoření aplikace konzoly pracovního postupu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6461a644bdedd3d391059cd8a3a17f887e77c6b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-workflow-console-application"></a>Postupy: vytvoření aplikace konzoly pracovního postupu

Windows Workflow Foundation (WF) umožňuje vytvořit pracovní postupy pro provádění systému nebo lidského procesy. Návrháři pracovních postupů Windows poskytuje návrhové ploše pro vytváření těchto pracovních postupů. Návrhář postupu provádění lze použít k vytváření pracovních postupů v sadě Visual Studio nebo může být integrovaná do jiných aplikací, které opětovným hostováním návrháře.

Toto téma popisuje postup použití návrháře pracovních postupů v sadě Visual Studio 2010 pro vytvoření pracovního postupu v konzolové aplikaci.

## <a name="to-create-a-workflow-console-application"></a>K vytvoření konzolové aplikace pracovního postupu

1.  Spusťte sadu Visual Studio 2010.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  V **nainstalovaných šablonách** podokně, vyberte **pracovního postupu** buď z **Visual C#** nebo **jazyka Visual Basic** seskupení, v závislosti na vaší jazykové předvolby.

4.  V prostředním podokně vyberte **pracovního postupu konzolové aplikace**.

5.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

6.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** pole, zadejte název nové řešení. Klikněte na tlačítko **OK** k vytvoření aplikace.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v sadě Visual Studio 2010, klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak  **Nový projekt** otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici pracovního postupu v jazyce XAML a definice aplikace konzoly je ve zdrojovém kódu. Návrhář postupu provádění se zobrazí na plátno pro pracovní postup, který jste vytvořili.

9. Chcete-li vytvořit pracovní postup, přetáhněte aktivity nebo jiné položky pracovního postupu z **sada nástrojů** na návrhovou plochu do svého pracovního postupu.

## <a name="see-also"></a>Viz také

- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)